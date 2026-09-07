---
name: Track Department of State press releases and briefings
description: >-
  Pull new press releases, press briefings and remarks from state.gov as structured JSON instead of
  scraping the website, filter them by date, and resolve each one back to its public URL.
api: openapi/department-of-state-state-gov-content-openapi.yml
operations:
  - listStatePressRelease
  - getStatePressRelease
  - listStateBriefing
  - getStateBriefing
  - listStateAuthorGroups
auth: none
base: https://www.state.gov/wp-json
---

# Track State Department press releases and briefings

The Department publishes both as WordPress custom post types. They are readable anonymously — no key,
no registration. This is the supported alternative to scraping https://www.state.gov/press-releases/.

## 1. Get the most recent releases

Call `listStatePressRelease`:

```
GET https://www.state.gov/wp-json/wp/v2/state_press_release
    ?per_page=25
    &orderby=date&order=desc
    &_fields=id,date_gmt,modified_gmt,slug,link,title,state_bureau
```

**Always send `_fields`.** Without it each item carries `content.rendered`, the full HTML of the
release, and a single page runs to hundreds of kilobytes. Add `content` back only for the items you
actually intend to read.

Read `X-WP-Total` and `X-WP-TotalPages` from the response headers to know how far the collection
goes. There is no cursor and no `next` link in the body — the body is a bare JSON array.

## 2. Poll for what is new

Do not re-walk the collection. Filter on the server:

```
GET https://www.state.gov/wp-json/wp/v2/state_press_release?after=2026-09-01T00:00:00&orderby=date&order=asc
```

Use `modified_after` instead of `after` if you care about edits to already-published releases —
the Department does revise them, and `modified_gmt` moves when it does.

Store `date_gmt`, not `date`. `date` is Eastern time; `date_gmt` is unambiguous.

## 3. Do the same for briefings

`listStateBriefing` against `/wp/v2/state_briefing` takes the identical parameters. Briefings are
where transcripts of the daily press briefing and the Secretary's remarks live, so a monitor that
only watches press releases misses most of what the Department says.

## 4. Read one item in full

Once you have an `id`, call `getStatePressRelease`:

```
GET https://www.state.gov/wp-json/wp/v2/state_press_release/703316?_embed
```

`_embed` inlines the linked terms and featured media in the same round trip instead of making you
walk the id arrays.

## Rules that will bite you

- **`title.rendered` and `content.rendered` are HTML.** Titles carry entities — you will see
  `Public Schedule &#8211; September 7, 2026`. Decode entities and strip tags before display.
- **`id` is not unique across content types.** Press release 703316 and report 703316 are different
  items. Always carry the content type alongside the id. Prefer `slug` when you need a durable
  reference; `?slug=public-schedule-september-7-2026` resolves without an id.
- **`author` is a dead end.** `https://www.state.gov/wp-json/wp/v2/users` is blocked at the edge with
  a 403 HTML page, so the numeric author id cannot be resolved anonymously. Use the
  `state_author_groups` taxonomy (`listStateAuthorGroups`) for attribution instead.
- **No rate limit is published, so set your own.** robots.txt asks for `crawl-delay: 5`. Keep
  concurrency at 1 and pace yourself; there is no 429 and no Retry-After to tell you when you have
  gone too far — the edge simply starts returning 403 HTML.
- **Errors are `{code, message, data.status}`,** not RFC 9457. Match on `code`:
  `rest_post_invalid_id` means the id is wrong for this type, `rest_no_route` means the route itself
  is gone. See `errors/department-of-state-problem-types.yml`.
