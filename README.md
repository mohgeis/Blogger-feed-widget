# Blogger-feed-widget

Reusable Blogger feed page for embedding on Google Sites (or any site that can iframe a URL).

One hosted page. Many **source blogs** and many **destination sites** — configured by URL parameters.

- Repo: https://github.com/mohgeis/Blogger-feed-widget  
- Live: https://mohgeis.github.io/Blogger-feed-widget/

Default blog (if you open the page with no params):  
`https://blog.sudanassociation.se`

## Embed URL shape

```text
https://mohgeis.github.io/Blogger-feed-widget/?blog=BLOG_URL&cols=2&rows=3&images=1
```

**Posts shown = `cols` × `rows`** (default 2×3 = 6).

### Parameters

| Param | Default | Meaning |
|-------|---------|---------|
| `blog` | `https://blog.sudanassociation.se` | Source Blogger homepage (or full feed URL) |
| `cols` | `2` | Max columns (1–4) |
| `rows` | `3` | Max rows (1–10) |
| `images` | `1` | Show post images (`1`/`true` or `0`/`false`) |
| `title` | Senaste artiklar / … | Header text |
| `more` | Alla inlägg → | “All posts” link label |
| `label` | _(empty)_ | Optional Blogger label filter |
| `accent` | `#0C4466` | Main color |
| `accent2` | `#50b090` | Accent / date color |
| `excerpt` | `140` | Excerpt length |
| `hideHeader` | `0` | `1` = hide title row |
| `max` | _(optional)_ | Override total posts instead of `cols × rows` |

### Examples

2 columns × 2 rows, with images (default):

```text
https://mohgeis.github.io/Blogger-feed-widget/?blog=https://blog.sudanassociation.se&cols=2&rows=2
```

3 columns × 2 rows, **without** images:

```text
https://mohgeis.github.io/Blogger-feed-widget/?blog=https://blog.sudanassociation.se&cols=3&rows=2&images=0
```

Another blog, 1 column × 5 rows:

```text
https://mohgeis.github.io/Blogger-feed-widget/?blog=https://myotherblog.blogspot.com&cols=1&rows=5&title=News
```

## Enable GitHub Pages

1. Repo **Settings → Pages**
2. Source: **Deploy from a branch**
3. Branch: `main` / `/ (root)` → Save
4. Open https://mohgeis.github.io/Blogger-feed-widget/

## Google Sites

Insert → Embed → **By URL** → paste the full URL **including** query params → Publish.

Source blog must be public, with **Settings → Site feed** enabled.
