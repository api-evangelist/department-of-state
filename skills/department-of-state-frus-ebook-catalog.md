---
name: Search and download the Foreign Relations of the United States series
description: >-
  Use the Office of the Historian's OPDS Ebook Catalog API to browse, search and fetch download links
  for the FRUS series — the official documentary record of U.S. foreign policy.
api: https://history.state.gov/api/v1/catalog
auth: none
base: https://history.state.gov/api/v1
---

# Search and download the FRUS ebook catalog

The Office of the Historian publishes the only *documented*, first-party API the Department of State
currently offers: an [OPDS Catalog 1.1](https://history.state.gov/developer/catalog) feed of the
*Foreign Relations of the United States* series. It is Atom XML, not JSON, and it needs no key.

## Operations

| Purpose | Request |
|---|---|
| Catalog root | `GET https://history.state.gov/api/v1/catalog` |
| Everything, in series order | `GET https://history.state.gov/api/v1/catalog/all` |
| 10 most recently published volumes | `GET https://history.state.gov/api/v1/catalog/recent` |
| Browse by subject | `GET https://history.state.gov/api/v1/catalog/browse?tag={value}` |
| Free-text search | `GET https://history.state.gov/api/v1/catalog/search?q={value}` |

## 1. Start at the root

```
GET https://history.state.gov/api/v1/catalog
```

The root is a navigation feed: `<link>` elements with
`type="application/atom+xml;profile=opds-catalog;kind=acquisition"` pointing at the four sub-feeds.
Follow the links rather than hard-coding paths — that is the point of OPDS.

## 2. Search

```
GET https://history.state.gov/api/v1/catalog/search?q=vietnam
```

The Office documents the query as **Lucene query syntax**, so `q=vietnam AND 1964`, field terms and
quoted phrases all work. An empty result set is a well-formed feed with no `<entry>` elements, not an
error.

## 3. Get the files

Each `<entry>` carries acquisition links. Match on the `type` attribute:

- `application/epub+zip`
- `application/x-mobipocket-ebook`
- `application/pdf`
- `image/jpeg` — the cover image

## Rules that will bite you

- **Parse it as Atom, not JSON.** Content-type is `text/xml`; the root element is
  `<feed xmlns="http://www.w3.org/2005/Atom">`.
- **`/catalog/all` is about 880KB.** Fetch it once and cache; use `/recent` for polling.
- **Link back, do not mirror.** The Office asks explicitly: *"Please link back to the ebooks files on
  this server, so that readers can always receive the most up-to-date version."* Honour it — the
  volumes are revised.
- **No key, no quota, no published limit.** There is also no status page and no SLA. Pace yourself.
- **Feedback goes to a real place.** `history@state.gov`, or issues at
  `https://github.com/HistoryAtState/Feedback`. The underlying source data is open at
  `https://github.com/HistoryAtState` (FRUS as TEI XML, people, terms, milestones).
