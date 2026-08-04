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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

The U.S. Department of State leads U.S. foreign policy, conducts diplomacy with foreign governments, issues U.S. passports and visas, supports U.S. citizens abroad, and publishes country-specific information and travel advisories. The Department does not currently operate a unified developer portal; integrators work from public RSS feeds, web pages, the Foreign Affairs Manual, and references to internal systems (ConsularLookout / CLASS, eCASE) that are not publicly accessible.

This repository inventories that landscape as an APIs.yml index plus generated artifacts (vocabulary, JSON-LD, capabilities, rules) for the public surfaces. No OpenAPI specs are published in this repo because there are no formal, documented REST contracts to specify - including a fabricated spec would misrepresent what the agency offers.

**APIs.yml:** [apis.yml](https://raw.githubusercontent.com/api-evangelist/department-of-state/main/apis.yml)

## Scope

- **Type:** Index
- **Position:** Consuming
- **Access:** 3rd-Party

## Tags

- Federal Government
- Foreign Affairs
- Travel
- Consular
- Visas
- Passports

## Repository Layout

- [`apis.yml`](apis.yml) — APIs.json/yml index of public and referenced State Department surfaces
- [`json-ld/`](json-ld/) — JSON-LD context aligning State Department terms to schema.org
- [`vocabulary/`](vocabulary/) — Controlled vocabulary covering travel, consular, visas, passports, embassies, and internal-system references
- [`capabilities/`](capabilities/) — Capability catalog
- [`rules/`](rules/) — Attribution, advisory-freshness, PII, and government-internal boundary rules

## What's Catalogued

### Public Surfaces (Bureau of Consular Affairs)
- **Travel Advisories** (RSS available)
- **Country Information Pages**
- **Smart Traveler Enrollment Program (STEP)**
- **U.S. Visa Information**
- **U.S. Passport Services**

### Public Reference
- **Foreign Affairs Manual (FAM) and Handbook (FAH)**
- **State Department Open Data on data.gov**

### Government-Internal (Referenced Only)
- **ConsularLookout (CLASS)** — name-check system used in visa and passport adjudication
- **eCASE** — enterprise case-management platform used across State Department bureaus

## Why No OpenAPI Specs

The Department of State does not publish formal REST APIs with documented endpoints, schemas, or stable base URLs. Travel advisories are distributed via RSS; country information lives in web pages; status lookups (passport, visa) are account-bound web flows; ConsularLookout and eCASE are internal-only. Per the structural rule of this catalog, a spec is only generated where a real, documented contract exists.

If the Department publishes a developer portal in the future, OpenAPI specs will be added under an `openapi/` folder.

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
