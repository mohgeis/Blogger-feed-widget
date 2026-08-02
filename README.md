# Blogger-feed-widget

One hosted page. Many **source blogs** and many **destination sites** — configured by URL parameters.

Default blog (if you open the page with no params):  
`https://blog.sudanassociation.se`

## Embed URL shape

```text
https://YOUR_USERNAME.github.io/sa-blog-feed/?blog=BLOG_URL&max=6&title=Heading
```

### Parameters

| Param | Default | Meaning |
|-------|---------|---------|
| `blog` | `https://blog.sudanassociation.se` | Source Blogger homepage (or full feed URL) |
| `max` | `6` | Number of posts (1–25) |
| `title` | Senaste artiklar / … | Header text |
| `more` | Alla inlägg → | “All posts” link label |
| `label` | _(empty)_ | Optional Blogger label filter |
| `cols` | `2` | `1` or `2` columns |
| `accent` | `#0C4466` | Main color |
| `accent2` | `#50b090` | Accent / date color |
| `excerpt` | `140` | Excerpt length |
| `hideHeader` | `0` | `1` = hide title row |

### Examples

Sudanese Association (source) on Google Sites A:

```text
https://YOUR_USERNAME.github.io/sa-blog-feed/?blog=https://blog.sudanassociation.se&max=4
```

Another Blogger blog on Google Sites B:

```text
https://YOUR_USERNAME.github.io/sa-blog-feed/?blog=https://myotherblog.blogspot.com&title=News&max=3&accent=%23111111
```

Only posts with a label:

```text
https://YOUR_USERNAME.github.io/sa-blog-feed/?blog=https://blog.sudanassociation.se&label=نشاطات&max=5
```

## Publish once on GitHub Pages

1. Create public repo `sa-blog-feed`
2. Upload `index.html` + `.nojekyll`
3. Settings → Pages → branch `main` / root
4. Use different query strings per Google Site

## Google Sites

Insert → Embed → **By URL** → paste the full URL **including** `?blog=...` → Publish.

Source blog must be public, with **Settings → Site feed** enabled.
