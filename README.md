# Department of State

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
