# Department of State

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

The U.S. Department of State leads U.S. foreign policy, conducts diplomacy with foreign governments, issues U.S. passports and visas, supports U.S. citizens abroad, and publishes country-specific information and travel advisories. It operates no unified developer portal and issues no API keys, but it does serve several real, anonymous, machine-readable surfaces: the state.gov Content API at https://www.state.gov/wp-json, where 473 WordPress REST routes expose press releases, briefings, reports, biographies, bureaus and country and policy content as structured JSON with no credential; the Office of the Historian Ebook Catalog API, an OPDS Catalog 1.1 feed of the Foreign Relations of the United States series and the only surface the Department documents on a developer page of its own; a DCAT-US 3.0 open data catalog of 397 datasets at https://www.state.gov/data.json; and the Travel Advisories RSS feed. Discovery is the weak point rather than supply — none of the nine State hosts probed serves any /.well-known/ document, three of the four State APIs listed in the federal inventory have been retired without notice, and travel.state.gov and the Bureau of Consular Affairs data catalog refuse non-browser clients outright.

**Areas:** Federal Government · Foreign Affairs · Travel · Consular · Visa · Passports

## Department of State on APIs.io

Everything profiled for Department of State is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/department-of-state/](https://apis.io/providers/department-of-state/)** — or go straight to one of the APIs or properties below.

### APIs (12)

- [Office of the Historian Ebook Catalog API](https://apis.io/apis/department-of-state/historian-ebook-catalog-api/) — A RESTful, OPDS Catalog 1.1 feed of the Foreign Relations of the United States series — the official documentary record of major U.S. foreign policy…
- [Department of State Open Data Catalog](https://apis.io/apis/department-of-state/open-data-catalog/) — The Department's Project Open Data catalog, served as a single machine-readable DCAT-US 3.0 document at https://www.state.gov/data.json. 397 dataset entries…
- [State Department Travel Advisories](https://apis.io/apis/department-of-state/travel-advisories/) — Country-by-country travel advisories (Levels 1-4) issued by the Bureau of Consular Affairs, with RSS distribution.
- [Country Information Pages](https://apis.io/apis/department-of-state/country-information/) — Per-country pages covering entry/exit requirements, local laws, safety, health, and U.S. embassy contacts.
- [Smart Traveler Enrollment Program (STEP)](https://apis.io/apis/department-of-state/smart-traveler-enrollment-program/) — Voluntary enrollment system for U.S. citizens traveling or residing abroad to receive embassy alerts.
- [U.S. Visa Information](https://apis.io/apis/department-of-state/visa-information/) — Reference information on nonimmigrant and immigrant visa categories, processing times, and reciprocity schedules.
- [U.S. Passport Services](https://apis.io/apis/department-of-state/passport-services/) — Public-facing passport application, renewal, and status-check resources from the Bureau of Consular Affairs.
- [Foreign Affairs Manual (FAM) and Handbook (FAH)](https://apis.io/apis/department-of-state/foreign-affairs-manual/) — Department-wide policy and procedural manuals issued by the Office of Directives Management.
- [ConsularLookout (CLASS)](https://apis.io/apis/department-of-state/consular-lookout-class/) — Government-internal name-check system used during visa and passport adjudication. Referenced here for completeness; no public API.
- [eCASE Enterprise Case Management](https://apis.io/apis/department-of-state/ecase/) — State Department-wide enterprise case-management platform. Internal system; referenced here for organizational completeness.
- [State Department Open Data on data.gov](https://apis.io/apis/department-of-state/state-data-gov/) — Public datasets published by the State Department through the federal open-data catalog.
- [Department of State Website (WordPress REST)](https://apis.io/apis/department-of-state/state-gov-website-wordpress-rest/) — The public WordPress REST API (wp-json) of the Department of State website at www.state.gov: the route index of the site's content management system,…

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [department-of-state](https://apis.io/servers/department-of-state/department-of-state/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Department Of State Agentic Access](https://apis.io/agentic-access/department-of-state/department-of-state-agentic-access/)

#### JSON Schema (10)

The data models the API reads and writes.

- [state_biography](https://apis.io/schemas/department-of-state/department-of-state-state-biography/)
- [state_briefing](https://apis.io/schemas/department-of-state/department-of-state-state-briefing/)
- [state_bureau](https://apis.io/schemas/department-of-state/department-of-state-state-bureau/)
- [state_country](https://apis.io/schemas/department-of-state/department-of-state-state-country/)
- [state_ext_content](https://apis.io/schemas/department-of-state/department-of-state-state-ext-content/)
- [state_people](https://apis.io/schemas/department-of-state/department-of-state-state-people/)
- [state_policy_issue](https://apis.io/schemas/department-of-state/department-of-state-state-policy-issue/)
- [state_press_release](https://apis.io/schemas/department-of-state/department-of-state-state-press-release/)
- [state_report](https://apis.io/schemas/department-of-state/department-of-state-state-report/)
- [state_trip_travel](https://apis.io/schemas/department-of-state/department-of-state-state-trip-travel/)

#### JSON-LD (1)

Linked-data contexts for the provider's vocabulary.

- [State Context](https://apis.io/jsonld/department-of-state/state-context/)

#### Vocabulary (1)

The provider's domain terms, defined.

- [Department of State Vocabulary](https://apis.io/vocabularies/department-of-state/state-vocabulary/)

#### Governance rules (1)

Spectral rulesets for the provider's contracts.

- [Department of State — state rules](https://apis.io/rules/department-of-state/state-rules/)

#### Security (3)

Authentication, trust centre, and vulnerability disclosure.

- [Department Of State Authentication](https://apis.io/security/department-of-state/department-of-state-authentication/)
- [Department Of State Domain Security](https://apis.io/security/department-of-state/department-of-state-domain-security/)
- [Department Of State Vulnerability Disclosure](https://apis.io/security/department-of-state/department-of-state-vulnerability-disclosure/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Department Of State Plans Pricing](https://apis.io/plans/department-of-state/department-of-state-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Department Of State Rate Limits](https://apis.io/rate-limits/department-of-state/department-of-state-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Department Of State Finops](https://apis.io/finops/department-of-state/department-of-state-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.state.gov/)
- [Documentation](https://history.state.gov/developer/catalog)
- [API reference](https://www.state.gov/wp-json/)
- [Support](https://www.state.gov/contact-us/)
- [Blog](https://www.state.gov/blogs)
- [Security](https://www.state.gov/bureau-of-diplomatic-technology/vulnerability-disclosure-policy)
- [Terms of service](https://www.state.gov/copyright-information)
- [Privacy policy](https://www.state.gov/privacy-policy)
- [GitHub](https://github.com/usstatedept)

## API Evangelist rating

**Kin Score 28.0** — thin · rubric 0.24.0 · scored 2026-10-17

| Facet | Score |
|---|---|
| Discoverability | 53.6 |
| Contract quality | 6.7 |
| Contract governance | 18.2 |
| Operational transparency | 28.9 |
| Developer ergonomics | 44.6 |
| Access clarity | 21.1 |

**Agent readiness 11.3** — agent-aware

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | — |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | derived (partial credit) |
| OpenAPI Examples | — |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | — |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | yes |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |

**Regulatory alignment 30.4** — Government & Public Sector

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/department-of-state/](https://apis.io/providers/department-of-state/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Department of State: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/department-of-state/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
