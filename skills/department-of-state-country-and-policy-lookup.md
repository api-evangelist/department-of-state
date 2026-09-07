---
name: Look up Department of State country and policy content
description: >-
  Resolve a country or a policy issue to the Department's own landing content, the bureau that owns
  it, and the reports that cover it — using the state.gov taxonomies rather than guessing URLs.
api: openapi/department-of-state-state-gov-content-openapi.yml
operations:
  - listStateCountriesAndAreas
  - listStateCountry
  - getStateCountry
  - listStatePolicyIssues
  - listStateReport
  - listStateBureau
auth: none
base: https://www.state.gov/wp-json
---

# Look up country and policy content on state.gov

The Department models countries and policy issues as **taxonomies**, and attaches content to them by
term id. Resolving the term first is the whole trick — content queries take term ids, not names.

## 1. Resolve the country to a term id

```
GET https://www.state.gov/wp-json/wp/v2/state_countries_and_areas?search=Kenya&_fields=id,name,slug
```

`listStateCountriesAndAreas` returns the taxonomy terms. Take the `id`. Note this is the
**countries and areas taxonomy** — `state_country` (singular) is a separate *content type* holding
the country landing pages, and its ids are unrelated.

## 2. Find the content attached to it

Pass the term id to any content collection that carries that taxonomy:

```
GET https://www.state.gov/wp-json/wp/v2/state_country?state_countries_and_areas=<termId>
GET https://www.state.gov/wp-json/wp/v2/state_report?state_countries_and_areas=<termId>&_fields=id,date,slug,link,title
```

`listStateReport` is where the flagship annual reports live — Country Reports on Human Rights
Practices, International Religious Freedom, Trafficking in Persons. Filtering them by country term
is far more reliable than pattern-matching titles.

## 3. Do the same for a policy issue

```
GET https://www.state.gov/wp-json/wp/v2/state_policy_issues?search=climate&_fields=id,name,slug
GET https://www.state.gov/wp-json/wp/v2/state_report?state_policy_issues=<termId>
```

## 4. Find the owning bureau

```
GET https://www.state.gov/wp-json/wp/v2/state_bureau?search=Consular&_fields=id,slug,link,title
```

`listStateBureau` is a content type, one item per bureau or office, each with its own state.gov URL
in `link`.

## 5. Read one country page in full

```
GET https://www.state.gov/wp-json/wp/v2/state_country/<id>?_embed
```

## What this API does NOT cover

This is the state.gov policy and public-affairs surface. It is **not** consular information:

- **Travel advisories** are not here. The only machine-readable form is the RSS feed at
  `https://travel.state.gov/_res/rss/TAsTWs.xml` (RSS 2.0, one item per country with its level).
- **Country entry/exit requirements, visa and passport pages** live on travel.state.gov, which
  answers non-browser clients with a Cloudflare 403 challenge. There is no JSON equivalent.
- **Consular open data** is at `https://cadatacatalog.state.gov/` (CKAN). State's own `data.json`
  links resource downloads there, but every request from a non-browser client is challenged.

Do not conflate a state.gov `state_country` landing page with a travel.state.gov country information
page. They are different documents with different owners, and only the first is reachable here.
