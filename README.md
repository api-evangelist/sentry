# Sentry (sentry)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Sentry is a developer-first application monitoring platform that helps software teams discover, triage, and prioritize errors and performance issues in production. Sentry provides real-time error monitoring, performance tracing, session replay, profiling, and release tracking for web, mobile, and backend applications across 22+ platforms and languages.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/sentry/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/sentry/refs/heads/main/apis.yml)

## Scope

- **Type:** Index

## Tags

- Error Monitoring
- Debugging
- Observability
- Application Performance Management
- Developer Tools

## Timestamps

- **Created:** 2026-03-18
- **Modified:** 2026-05-19

## APIs

### Sentry Error Monitoring API

Sentry provides error monitoring and performance tracking REST APIs for software applications. APIs enable issue management, event retrieval, release tracking, alert configuration, and project administration. All endpoints are scoped to an organization. Current API version is v0.

- **Human URL:** [https://docs.sentry.io/api/](https://docs.sentry.io/api/)
- **Base URL:** `https://sentry.io/api/0`

#### Tags

- Error Monitoring
- Debugging
- Observability
- Application Performance Management

#### Properties

- [Documentation](https://docs.sentry.io/api/)
- [Reference](https://docs.sentry.io/api/)
- [Authentication](https://docs.sentry.io/api/auth/)
- [Rate Limits](https://docs.sentry.io/api/ratelimits/)
- [Getting Started](https://docs.sentry.io/api/guides/create-auth-token/)
- [OpenAPI](openapi/sentry-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/sentry-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/sentry-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Sentry SDK API

Sentry provides official SDKs for 22+ platforms including JavaScript, Python, PHP, .NET, Java, Go, Ruby, Rust, Android, Apple, React Native, Unity, and Unreal Engine. Each SDK provides error capture, performance monitoring, session replay, and profiling capabilities.

- **Human URL:** [https://docs.sentry.io/platforms/](https://docs.sentry.io/platforms/)

#### Tags

- Error Monitoring
- Debugging
- Observability
- Application Performance Management
- SDK

#### Properties

- [Documentation](https://docs.sentry.io/platforms/)
- [Reference](https://develop.sentry.dev/sdk/overview/)
- [Postman Collection](collections/sentry-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/sentry-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Sentry Integration Platform API

The Sentry Integration Platform API enables building public and internal integrations with Sentry. Supports OAuth2 with PKCE, device authorization flow for CLI/CI environments, webhook notifications, and custom alert actions for third-party applications.

- **Human URL:** [https://docs.sentry.io/api/integration/](https://docs.sentry.io/api/integration/)

#### Tags

- Error Monitoring
- Integrations
- Webhooks
- OAuth

#### Properties

- [Documentation](https://docs.sentry.io/api/integration/)
- [Authentication](https://docs.sentry.io/api/auth/)
- [AsyncAPI](asyncapi/sentry-webhooks-asyncapi.yml) — [AsyncAPI Specification](https://www.asyncapi.com/docs/reference/specification/latest)
- [Postman Collection](collections/sentry-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/sentry-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Arazzo Workflows](arazzo/) — [Arazzo Specification](https://spec.openapis.org/arazzo/latest.html)
- [LinkedIn](https://www.linkedin.com/company/getsentry)
- [Website](https://sentry.io/)
- [Portal](https://docs.sentry.io/api/)
- [Documentation](https://docs.sentry.io/api/)
- [Authentication](https://docs.sentry.io/api/auth/)
- [Rate Limits](https://docs.sentry.io/api/ratelimits/)
- [Getting Started](https://docs.sentry.io/api/guides/create-auth-token/)
- [Changelog](https://sentry.io/changelog/)
- [Status Page](https://status.sentry.io/)
- [Terms of Service](https://sentry.io/terms/)
- [Privacy Policy](https://sentry.io/legal/privacy/)
- [Blog](https://sentry.io/blog/)
- [S D Ks](https://docs.sentry.io/platforms/)
- [GitHub Organization](https://github.com/getsentry)
- [Developer Tools](https://sandbox.sentry.io/)
- [Pricing](https://sentry.io/pricing/)
- [Sign Up](https://sentry.io/signup/)
- [Login](https://sentry.io/auth/login/)
- [JSON Schema](json-schema/sentry-issue-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [J S O N L D Context](json-ld/sentry-context.jsonld)
- [JSON Structure](json-structure/sentry-issue-structure.json)
- [Vocabulary](vocabulary/sentry-vocabulary.yml)
- [Spectral Rules](rules/sentry-rules.yml)
- [Capabilities](capabilities/error-monitoring.yaml)
- [Features](undefined)
- [Integrations](https://sentry.io/integrations/)
- [L L Ms Txt](https://docs.sentry.io/llms.txt)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
