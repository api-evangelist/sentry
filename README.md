# Sentry

**URL:** [https://raw.githubusercontent.com/api-evangelist/sentry/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/sentry/refs/heads/main/apis.yml)

Sentry is a developer-first application monitoring platform that helps software teams discover, triage, and prioritize errors and performance issues in production. Sentry provides real-time error monitoring, performance tracing, session replay, profiling, and release tracking for web, mobile, and backend applications across 22+ platforms and languages.

## Timestamps

- **Created:** 2026-03-18
- **Modified:** 2026-05-02

## APIs

### Sentry Error Monitoring API

Sentry provides error monitoring and performance tracking REST APIs for software applications. APIs enable issue management, event retrieval, release tracking, alert configuration, and project administration. All endpoints are scoped to an organization. Current API version is v0.

**Human URL:** [https://docs.sentry.io/api/](https://docs.sentry.io/api/)
**Base URL:** `https://sentry.io/api/0`

#### Tags

Error Monitoring, Debugging, Observability, Application Performance Management

#### Properties

- [Documentation](https://docs.sentry.io/api/)
- [Authentication](https://docs.sentry.io/api/auth/)
- [Rate Limits](https://docs.sentry.io/api/ratelimits/)
- [Getting Started](https://docs.sentry.io/api/guides/create-auth-token/)
- [OpenAPI](openapi/sentry-api-openapi.yml)

---

### Sentry SDK API

Sentry provides official SDKs for 22+ platforms including JavaScript, Python, PHP, .NET, Java, Go, Ruby, Rust, Android, Apple, React Native, Unity, and Unreal Engine. Each SDK provides error capture, performance monitoring, session replay, and profiling capabilities.

**Human URL:** [https://docs.sentry.io/platforms/](https://docs.sentry.io/platforms/)

#### Tags

Error Monitoring, Debugging, Observability, Application Performance Management, SDK

#### Properties

- [Documentation](https://docs.sentry.io/platforms/)
- [Reference](https://develop.sentry.dev/sdk/overview/)

---

### Sentry Integration Platform API

The Sentry Integration Platform API enables building public and internal integrations with Sentry. Supports OAuth2 with PKCE, device authorization flow for CLI/CI environments, webhook notifications, and custom alert actions for third-party applications.

**Human URL:** [https://docs.sentry.io/api/integration/](https://docs.sentry.io/api/integration/)

#### Tags

Error Monitoring, Integrations, Webhooks, OAuth

#### Properties

- [Documentation](https://docs.sentry.io/api/integration/)
- [Authentication](https://docs.sentry.io/api/auth/)
- [AsyncAPI](asyncapi/sentry-webhooks-asyncapi.yml)

---

## Common Properties

- [Website](https://sentry.io/)
- [Portal](https://docs.sentry.io/api/)
- [Documentation](https://docs.sentry.io/api/)
- [Authentication](https://docs.sentry.io/api/auth/)
- [Rate Limits](https://docs.sentry.io/api/ratelimits/)
- [Getting Started](https://docs.sentry.io/api/guides/create-auth-token/)
- [Changelog](https://sentry.io/changelog/)
- [Status](https://status.sentry.io/)
- [Terms of Service](https://sentry.io/terms/)
- [Privacy Policy](https://sentry.io/legal/privacy/)
- [Blog](https://sentry.io/blog/)
- [SDKs](https://docs.sentry.io/platforms/)
- [GitHub Organization](https://github.com/getsentry)
- [Developer Sandbox](https://sandbox.sentry.io/)
- [Pricing](https://sentry.io/pricing/)

## Artifacts

### OpenAPI Specifications

| File | Description |
|------|-------------|
| [sentry-api-openapi.yml](openapi/sentry-api-openapi.yml) | Sentry REST API v0 — organizations, issues, events, projects, releases, alerts |

### AsyncAPI Specifications

| File | Description |
|------|-------------|
| [sentry-webhooks-asyncapi.yml](asyncapi/sentry-webhooks-asyncapi.yml) | Sentry Integration Platform webhooks — issues, errors, comments, installs, alerts |

### JSON Schemas

| File | Description |
|------|-------------|
| [sentry-issue-schema.json](json-schema/sentry-issue-schema.json) | JSON Schema for the Sentry Issue resource |

### JSON Structures

| File | Description |
|------|-------------|
| [sentry-issue-structure.json](json-structure/sentry-issue-structure.json) | Field-by-field structural documentation for the Issue resource |

### JSON-LD Context

| File | Description |
|------|-------------|
| [sentry-context.jsonld](json-ld/sentry-context.jsonld) | JSON-LD context mapping Sentry vocabulary to schema.org |

### Examples

| File | Description |
|------|-------------|
| [sentry-list-organizations-example.json](examples/sentry-list-organizations-example.json) | List organizations |
| [sentry-list-organization-issues-example.json](examples/sentry-list-organization-issues-example.json) | List and filter issues |
| [sentry-create-release-example.json](examples/sentry-create-release-example.json) | Create a release |
| [sentry-update-issue-example.json](examples/sentry-update-issue-example.json) | Update issue status |

### Rules

| File | Description |
|------|-------------|
| [sentry-rules.yml](rules/sentry-rules.yml) | Spectral ruleset enforcing Sentry API conventions |

### Capabilities

| File | Description |
|------|-------------|
| [capabilities/error-monitoring.yaml](capabilities/error-monitoring.yaml) | Unified error monitoring workflow — issue triage, release tracking, alerting |
| [capabilities/shared/sentry-api.yaml](capabilities/shared/sentry-api.yaml) | Per-API Naftiko consumed definition for the Sentry REST API |

### Vocabulary

| File | Description |
|------|-------------|
| [sentry-vocabulary.yml](vocabulary/sentry-vocabulary.yml) | Domain vocabulary for Sentry error monitoring concepts |

## Maintainers

**Email:** kin@apievangelist.com
