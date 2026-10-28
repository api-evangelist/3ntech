# 3N TECH

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

3N TECH (Suzhou 3N Biological Technology Co., Ltd.) is a Chinese eye-care medical-device maker founded in 2015 and headquartered in Suzhou Industrial Park BioBAY, with an international arm selling in Hong Kong and the United States. It develops active contact-lens care hardware built on its patented Electrophoresis-Disintegration ("Elepy") technology, and shipped the first contact-lens cleaner to hold an FDA 510(k) clearance for that mechanism. The company sells under two brands: 3N in mainland China and ReO2 internationally, through the 3N Eyecare direct-to-consumer storefront. 3N TECH publishes no developer program and no OpenAPI. Its only machine-readable, publicly callable surface is the agentic-commerce layer on its own storefront host: an anonymous UCP (Universal Commerce Protocol) merchant profile at /.well-known/ucp.json, an unauthenticated MCP endpoint at /api/ucp/mcp serving 13 cart, checkout, order and catalog tools, an llms.txt / agents.md pair of agent instructions, and Shopify Customer Account OAuth 2.0 / OpenID Connect discovery documents. That surface is platform-authored by Shopify and served under the company's domain, which this profile records explicitly rather than crediting it as first-party API design.

**Areas:** Company · Eye Care · Medical Devices · Consumer Health · Contact Lenses · E-Commerce · Agentic Commerce · Universal Commerce Protocol · MCP · Manufacturing

## 3N TECH on APIs.io

Everything profiled for 3N TECH is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/3ntech/](https://apis.io/providers/3ntech/)** — or go straight to one of the APIs or properties below.

### APIs (1)

- [3N Eyecare Agentic Commerce (UCP / MCP)](https://apis.io/apis/3ntech/3n-eyecare-agentic-commerce-ucp-mcp/) — The Universal Commerce Protocol shopping service 3N Eyecare exposes on its own storefront host. An anonymous JSON-RPC 2.0 MCP endpoint serves 13 tools for…

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [universal-commerce](https://apis.io/servers/3ntech/universal-commerce/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [3Ntech Authentication](https://apis.io/security/3ntech/3ntech-authentication/)
- [3Ntech Domain Security](https://apis.io/security/3ntech/3ntech-domain-security/)

#### OAuth scopes (1)

The permissions the API asks for.

- [3Ntech Scopes](https://apis.io/scopes/3ntech/3ntech-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [3Ntech Plans Pricing](https://apis.io/plans/3ntech/3ntech-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [3Ntech Rate Limits](https://apis.io/rate-limits/3ntech/3ntech-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.3neyecare.com/)
- [Documentation](https://www.3neyecare.com/agents.md)
- [Sign up](https://account.3neyecare.com/)
- [Support](https://www.3neyecare.com/pages/contact)
- [Blog](https://www.3neyecare.com/blogs/news)
- [Terms of service](https://www.3neyecare.com/policies/terms-of-service)
- [Privacy policy](https://www.3neyecare.com/policies/privacy-policy)

## API Evangelist rating

**Kin Score 25.7** — emerging · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 75.0 |
| Contract quality | 0.0 |
| Contract governance | 18.2 |
| Operational transparency | 0.0 |
| Developer ergonomics | 30.4 |
| Access clarity | 34.2 |

**Agent readiness 23.7** — agent-aware

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | — |
| Agentic Access | — |
| Reversibility Documented | — |
| MCP Server | platform (partial credit) |
| Auth Clarity | served (partial credit) |
| Idempotency | — |
| Error Semantics | documented (partial credit) |
| OpenAPI Examples | — |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | — |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | served (partial credit) |
| Protected Resource Metadata | verified |
| Dynamic Client Registration | — |
| Agentic Commerce | platform (partial credit) |
| Pagination Ratio | na |
| Operation Distinctiveness | na |

**Regulatory alignment 32.8** — Health

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/3ntech/](https://apis.io/providers/3ntech/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for 3N TECH: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/3ntech/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
