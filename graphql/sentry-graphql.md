# Sentry GraphQL Schema

## Overview

Sentry does not currently expose a public GraphQL API. Their external developer API is a REST API versioned at `/api/0/`. This directory contains a **conceptual GraphQL SDL** (`sentry-schema.graphql`) that represents Sentry's core domain model as a type system, derived from:

- The Sentry REST API v0 — https://docs.sentry.io/api/
- OpenAPI specification (`openapi/sentry-api-openapi.yml`)
- JSON Schema artifacts (`json-schema/sentry-issue-schema.json`)
- Domain vocabulary (`vocabulary/sentry-vocabulary.yml`)
- Public Sentry source code — https://github.com/getsentry/sentry

Sentry's internal codebase does use GraphQL — but only as a **client** to query GitHub's GraphQL API (e.g., for blame data and Copilot integrations). No GraphQL server endpoint is exposed to external developers as of June 2026.

## Schema Source

**Type:** Conceptual data model (REST-derived SDL)
**Endpoint:** None (no public GraphQL endpoint)
**SDL file:** `sentry-schema.graphql`

## Root Types

### Query

| Field | Description |
|---|---|
| `organizations` | List organizations accessible to the authenticated user |
| `organization(slug)` | Retrieve a single organization |
| `issues(organizationSlug, ...)` | List issues with filtering and pagination |
| `issue(organizationSlug, issueId)` | Retrieve a single issue |
| `issueEvents(organizationSlug, issueId)` | List events for an issue |
| `projects(organizationSlug)` | List projects within an organization |
| `project(organizationSlug, projectSlug)` | Retrieve a single project |
| `releases(organizationSlug)` | List releases |
| `alertRules(organizationSlug)` | List alert rules |
| `teams(organizationSlug)` | List teams |
| `team(organizationSlug, teamSlug)` | Retrieve a single team |
| `members(organizationSlug)` | List organization members |
| `integrations(organizationSlug)` | List third-party integrations |
| `deploys(organizationSlug, releaseVersion)` | List deploys for a release |
| `monitors(organizationSlug)` | List cron monitors |

### Mutation

| Field | Description |
|---|---|
| `updateIssue` | Update status, assignee, or priority of an issue |
| `deleteIssue` | Permanently delete an issue |
| `createRelease` | Create a new release with commits |
| `createDeploy` | Record a deploy for a release |

## Core Types (32 total)

### Organization Hierarchy

- **Organization** — Top-level container; owns projects, teams, members, alert rules, and releases.
- **Project** — Application or service container; holds DSN, platform, and linked releases.
- **Team** — Group of members responsible for projects; can be assigned issues.
- **Member** — A user's membership record within an organization, including role.
- **User** — A Sentry user account with authentication metadata.

### Error Tracking

- **Issue** — Aggregation of similar events grouped by fingerprint. Has status, priority, assignee, and event history.
- **Event** — A single error occurrence with full stack trace, breadcrumbs, user context, tags, and SDK metadata.
- **IssueConnection** — Paginated issue list with cursor-based navigation.

### Release & Deployment

- **Release** — Named version with commit history, deploy count, and linked projects.
- **Deploy** — A specific deployment of a release to an environment (production, staging, etc.).
- **Commit** — Individual commit record linked to a release, with author and repository.

### Alerting

- **AlertRule** — Metric or issue alert with dataset, query, thresholds, and triggers.
- **AlertTrigger** — Threshold condition (warning or critical) within an alert rule.
- **AlertAction** — Notification target for a trigger (Slack, email, PagerDuty, etc.).

### Observability

- **Monitor** — Cron job health monitor that alerts on missed or late check-ins.
- **MonitorEnvironment** — Per-environment status and timing for a monitor.

### Integration

- **Integration** — Third-party service connection (GitHub, Slack, Jira, PagerDuty, etc.).
- **IntegrationProvider** — Provider metadata for an integration.

### Context & Metadata

- **EventContexts** — Structured device, OS, runtime, browser, GPU, app, and trace contexts.
- **TraceContext** — Distributed tracing identifiers attached to an event.
- **SdkInfo** — Sentry SDK name, version, and package details.
- **EventUser** — Affected user captured at event time.
- **IssueMetadata** — Exception type/value and source location for an issue.
- **IssueTagStat** — Tag key/name and total value count for an issue.

### Scalar Types

- **DateTime** — ISO-8601 date-time string.
- **JSON** — Arbitrary JSON value for extensible context fields.

## Enums

| Enum | Values |
|---|---|
| `SeverityLevel` | `FATAL`, `ERROR`, `WARNING`, `INFO`, `DEBUG` |
| `IssueStatus` | `RESOLVED`, `UNRESOLVED`, `IGNORED`, `RESOLVED_IN_NEXT_RELEASE` |
| `IssueType` | `ERROR`, `CSP`, `HPKP`, `EXPECTCT`, `EXPECTSTAPLE`, `PERFORMANCE`, `DEFAULT` |
| `Priority` | `CRITICAL`, `HIGH`, `MEDIUM`, `LOW` |
| `IssueSortOrder` | `DATE`, `NEW`, `PRIORITY`, `FREQ`, `USER` |
| `OrganizationRole` | `OWNER`, `MANAGER`, `ADMIN`, `MEMBER`, `BILLING` |
| `AlertDataset` | `EVENTS`, `TRANSACTIONS`, `SESSIONS`, `METRICS` |
| `AlertRuleStatus` | `PENDING`, `TRIGGERED`, `RESOLVED` |
| `IntegrationStatus` | `ACTIVE`, `DISABLED`, `PENDING_DELETION` |
| `MonitorStatus` | `ACTIVE`, `DISABLED`, `OK`, `ERROR`, `MISSED_CHECKIN`, `TIMED_OUT`, ... |
| `MonitorType` | `CRON_JOB` |
| `EventEntryType` | `EXCEPTION`, `STACKTRACE`, `BREADCRUMBS`, `REQUEST`, `SPANS`, ... |

## REST API Mapping

The following table maps GraphQL queries to the equivalent REST endpoints:

| GraphQL | REST Endpoint |
|---|---|
| `organizations` | `GET /api/0/organizations/` |
| `organization(slug)` | `GET /api/0/organizations/{slug}/` |
| `issues(organizationSlug)` | `GET /api/0/organizations/{slug}/issues/` |
| `issue(organizationSlug, issueId)` | `GET /api/0/organizations/{slug}/issues/{id}/` |
| `issueEvents` | `GET /api/0/organizations/{slug}/issues/{id}/events/` |
| `projects(organizationSlug)` | `GET /api/0/organizations/{slug}/projects/` |
| `project` | `GET /api/0/projects/{org}/{project}/` |
| `releases(organizationSlug)` | `GET /api/0/organizations/{slug}/releases/` |
| `alertRules(organizationSlug)` | `GET /api/0/organizations/{slug}/alert-rules/` |
| `updateIssue` | `PUT /api/0/organizations/{slug}/issues/{id}/` |
| `deleteIssue` | `DELETE /api/0/organizations/{slug}/issues/{id}/` |
| `createRelease` | `POST /api/0/organizations/{slug}/releases/` |
| `createDeploy` | `POST /api/0/organizations/{slug}/releases/{ver}/deploys/` |

## Authentication

Sentry's REST API (and by extension this conceptual schema) uses:

- **Auth Token** — `Authorization: Bearer TOKEN` or `Authorization: Token TOKEN`
- **OAuth 2.0** — For Integration Platform integrations via Sentry Apps
- **Org Auth Tokens** — Prefixed `sntryu_`, recommended for CI/CD

## References

- REST API Reference: https://docs.sentry.io/api/
- Authentication Guide: https://docs.sentry.io/api/auth/
- Developer Documentation: https://develop.sentry.dev/
- Sentry Source Code: https://github.com/getsentry/sentry
