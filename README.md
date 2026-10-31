# Pynt

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
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Pynt is an API security testing platform that discovers and secures APIs, LLM endpoints and MCP servers. It wraps a team's existing functional tests — or proxies live traffic — and runs automated attack simulations against whatever API surface it observes, covering business-logic flaws, injection, mass assignment, authentication bypass, SSRF, GraphQL introspection and alias overloading, LLM prompt injection and sensitive-data exposure. Pynt builds an API catalog from Swagger/OpenAPI definitions, Postman collections, API gateways, code repositories and eBPF live-traffic capture, scores each endpoint for risk, applies LLM false-positive and business-impact analysis to its findings, and generates automated penetration-test reports. It is delivered as a Python CLI that manages a Docker container, with integrations across Postman, Burp Suite, Insomnia, ReadyAPI, a dozen test frameworks, and the major CI/CD platforms. Pynt exposes a public REST API at api.pynt.io.

**Areas:** API Testing · API Security · Security · Application Security · DAST · API Discovery · Vulnerability Management · Penetration Testing · DevSecOps · LLM Security · MCP Security · Platform

## Pynt on APIs.io

Everything profiled for Pynt is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/pynt/](https://apis.io/providers/pynt/)** — or go straight to one of the APIs or properties below.

### APIs (32)

- [Pynt Alive API](https://apis.io/apis/pynt/pynt-alive-api/) — The Alive API from Pynt — 1 operation(s) for alive.
- [Pynt API Key API](https://apis.io/apis/pynt/pynt-api-key-api/) — The api-key API from Pynt — 2 operation(s) for api-key.
- [Pynt Application API](https://apis.io/apis/pynt/pynt-application-api/) — The application API from Pynt — 21 operation(s) for application.
- [Pynt Artifacts API](https://apis.io/apis/pynt/pynt-artifacts-api/) — The artifacts API from Pynt — 2 operation(s) for artifacts.
- [Pynt Auth API](https://apis.io/apis/pynt/pynt-auth-api/) — The auth API from Pynt — 4 operation(s) for auth.
- [Pynt Aws Marketplace API](https://apis.io/apis/pynt/pynt-aws-marketplace-api/) — The aws-marketplace API from Pynt — 2 operation(s) for aws-marketplace.
- [Pynt Config API](https://apis.io/apis/pynt/pynt-config-api/) — The config API from Pynt — 1 operation(s) for config.
- [Pynt Endpoint Group API](https://apis.io/apis/pynt/pynt-endpoint-group-api/) — The endpoint-group API from Pynt — 4 operation(s) for endpoint-group.
- [Pynt Endpoint Llm Analysis API](https://apis.io/apis/pynt/pynt-endpoint-llm-analysis-api/) — The endpoint-llm-analysis API from Pynt — 1 operation(s) for endpoint-llm-analysis.
- [Pynt Event Logs API](https://apis.io/apis/pynt/pynt-event-logs-api/) — The event-logs API from Pynt — 1 operation(s) for event-logs.
- [Pynt Evidence API](https://apis.io/apis/pynt/pynt-evidence-api/) — The evidence API from Pynt — 1 operation(s) for evidence.
- [Pynt Integrations API](https://apis.io/apis/pynt/pynt-integrations-api/) — The integrations API from Pynt — 1 operation(s) for integrations.
- [Pynt Invite API](https://apis.io/apis/pynt/pynt-invite-api/) — The invite API from Pynt — 4 operation(s) for invite.
- [Pynt Jobs API](https://apis.io/apis/pynt/pynt-jobs-api/) — The jobs API from Pynt — 1 operation(s) for jobs.
- [Pynt Legacy API](https://apis.io/apis/pynt/pynt-legacy-api/) — The legacy API from Pynt — 3 operation(s) for legacy.
- [Pynt Llm Prompt API](https://apis.io/apis/pynt/pynt-llm-prompt-api/) — The llm-prompt API from Pynt — 2 operation(s) for llm-prompt.
- [Pynt Nats API](https://apis.io/apis/pynt/pynt-nats-api/) — The nats API from Pynt — 3 operation(s) for nats.
- [Pynt Notification Rules API](https://apis.io/apis/pynt/pynt-notification-rules-api/) — The notification-rules API from Pynt — 2 operation(s) for notification-rules.
- [Pynt Organization API](https://apis.io/apis/pynt/pynt-organization-api/) — The organization API from Pynt — 4 operation(s) for organization.
- [Pynt Postman API](https://apis.io/apis/pynt/pynt-postman-api/) — The postman API from Pynt — 2 operation(s) for postman.
- [Pynt Postman Proxy API](https://apis.io/apis/pynt/pynt-postman-proxy-api/) — The postman-proxy API from Pynt — 1 operation(s) for postman-proxy.
- [Pynt Scan API](https://apis.io/apis/pynt/pynt-scan-api/) — The scan API from Pynt — 26 operation(s) for scan.
- [Pynt Scan Business Impact Analysis API](https://apis.io/apis/pynt/pynt-scan-business-impact-analysis-api/) — The scan-business-impact-analysis API from Pynt — 2 operation(s) for scan-business-impact-analysis.
- [Pynt Scan False Positive Analysis API](https://apis.io/apis/pynt/pynt-scan-false-positive-analysis-api/) — The scan-false-positive-analysis API from Pynt — 2 operation(s) for scan-false-positive-analysis.
- [Pynt Scan Profile API](https://apis.io/apis/pynt/pynt-scan-profile-api/) — The scan-profile API from Pynt — 1 operation(s) for scan-profile.
- [Pynt Scan Schedule API](https://apis.io/apis/pynt/pynt-scan-schedule-api/) — The scan-schedule API from Pynt — 4 operation(s) for scan-schedule.
- [Pynt Tag API](https://apis.io/apis/pynt/pynt-tag-api/) — The tag API from Pynt — 1 operation(s) for tag.
- [Pynt Ticketing API](https://apis.io/apis/pynt/pynt-ticketing-api/) — The ticketing API from Pynt — 3 operation(s) for ticketing.
- [Pynt Traffic Collector API](https://apis.io/apis/pynt/pynt-traffic-collector-api/) — The traffic-collector API from Pynt — 2 operation(s) for traffic-collector.
- [Pynt Traffic Filter API](https://apis.io/apis/pynt/pynt-traffic-filter-api/) — The traffic-filter API from Pynt — 1 operation(s) for traffic-filter.
- [Pynt User API](https://apis.io/apis/pynt/pynt-user-api/) — The user API from Pynt — 3 operation(s) for user.
- [Pynt Vulnerability Instance API](https://apis.io/apis/pynt/pynt-vulnerability-instance-api/) — The vulnerability-instance API from Pynt — 5 operation(s) for vulnerability-instance.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Pynt Webhooks](https://apis.io/asyncapis/pynt/pynt-webhooks/)

#### Overlays (1)

OpenAPI overlays, including conversational phrasing for each operation.

- [Pynt Openapi Overlay](https://apis.io/overlays/pynt/pynt-openapi-overlay/)

#### Security (4)

Authentication, trust centre, and vulnerability disclosure.

- [Pynt Authentication](https://apis.io/security/pynt/pynt-authentication/)
- [Pynt Domain Security](https://apis.io/security/pynt/pynt-domain-security/)
- [Pynt Trust Center](https://apis.io/security/pynt/pynt-trust-center/)
- [Pynt Vulnerability Disclosure](https://apis.io/security/pynt/pynt-vulnerability-disclosure/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Pynt Plans Pricing](https://apis.io/plans/pynt/pynt-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Pynt Rate Limits](https://apis.io/rate-limits/pynt/pynt-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Pynt Finops](https://apis.io/finops/pynt/pynt-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.pynt.io/)
- [Documentation](https://docs.pynt.io/documentation)
- [Getting started](https://docs.pynt.io/documentation/api-security-testing/prerequisites-for-running-pynt-scans)
- [Sign up](https://www.pynt.io/get-free-api-pentest)
- [Support](https://www.pynt.io/contact-us)
- [Blog](https://www.pynt.io/blog)
- [Security](https://github.com/pynt-io/pynt/blob/main/SECURITY.md)
- [Compliance](https://www.pynt.io/trust-center)
- [Terms of service](https://www.pynt.io/terms)
- [Privacy policy](https://www.pynt.io/privacy-policy)
- [GitHub](https://github.com/pynt-io)

## API Evangelist rating

**Kin Score 51.2** — developing · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 73.2 |
| Contract quality | 49.5 |
| Contract governance | 4.5 |
| Operational transparency | 21.1 |
| Developer ergonomics | 68.5 |
| Access clarity | 50.0 |

**Agent readiness 25.3** — agent-aware

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | — |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | verified |
| OpenAPI Examples | — |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | derived (partial credit) |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | — |
| Operation Distinctiveness | mostly (partial credit) |

**Regulatory alignment 35.3** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/pynt/](https://apis.io/providers/pynt/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Pynt: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/pynt/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
