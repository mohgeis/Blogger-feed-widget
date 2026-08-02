# Blogger-feed-widget

Reusable Blogger feed page for embedding on Google Sites (or any site that can iframe a URL).

One hosted page. Many **source blogs** and many **destination sites** — configured by URL parameters.

- Repo: https://github.com/mohgeis/Blogger-feed-widget  
- Live: https://mohgeis.github.io/Blogger-feed-widget/

Default blog (if you open the page with no params):  
`https://www.softolite.io`

## Embed URL shape

```text
https://mohgeis.github.io/Blogger-feed-widget/?blog=BLOG_URL&cols=2&rows=3&images=1
```

**Posts shown = `cols` × `rows`** (default 2×3 = 6).

### Parameters

| Param | Default | Meaning |
|-------|---------|---------|
| `blog` | `https://www.softolite.io` | Source Blogger homepage (or full feed URL) |
| `cols` | `2` | Max columns (1–4) |
| `rows` | `3` | Max rows (1–10) |
| `images` | `1` | Show post images (`1`/`true` or `0`/`false`) |
| `imageSource` | `auto` | Which image to use (see below) |

### Image source (`imageSource`)

Blogger’s feed thumbnail is often **not** the main/featured image when a post has several pictures.

| Value | Behavior |
|-------|----------|
| `auto` (default) | Show feed image first, then upgrade to the post’s **main featured image** (`og:image`) |
| `og` | Use the main featured image only |
| `content` | First image from the feed HTML body (needs Full / Until jump break feed) |
| `thumb` | Blogger `media$thumbnail` only (fast, may be wrong if multiple images) |
| `title` | Senaste artiklar / … | Header text |
| `more` | Alla inlägg → | “All posts” link label |
| `label` | _(empty)_ | Optional Blogger label filter |
| `accent` | `#0C4466` | Main color |
| `accent2` | `#50b090` | Accent / date color |
| `excerpt` | `90` | Excerpt length (`0` = hide excerpts, shorter embed) |
| `compact` | `1` | Tighter spacing for Google Sites embeds (`0` = roomier) |
| `hideHeader` | `0` | `1` = hide title row |
| `max` | _(optional)_ | Override total posts instead of `cols × rows` |

### Examples

2 columns × 2 rows, with images (uses default blog):

```text
https://mohgeis.github.io/Blogger-feed-widget/?cols=2&rows=2
```

3 columns × 2 rows, **without** images:

```text
https://mohgeis.github.io/Blogger-feed-widget/?cols=3&rows=2&images=0
```

Another blog, 1 column × 5 rows:

```text
https://mohgeis.github.io/Blogger-feed-widget/?blog=https://blog.sudanassociation.se&cols=1&rows=5&title=News
```

## Enable GitHub Pages

1. Repo **Settings → Pages**
2. Source: **Deploy from a branch**
3. Branch: `main` / `/ (root)` → Save
4. Open https://mohgeis.github.io/Blogger-feed-widget/

## Google Sites — two options

### Option A (recommended): Embed HTML code

Better control of layout; usually feels more “built into” the page.

1. Open [`google-sites-embed.html`](google-sites-embed.html) in this repo  
2. Edit the `CONFIG` object (`blog`, `cols`, `rows`, titles, colors)  
3. Copy **everything below the top comment**  
4. Google Sites → **Insert → Embed → Embed code** → paste → Insert  
5. Drag the embed box a bit taller if a scrollbar still shows → **Publish**

Google Sites still wraps custom HTML in a sandbox iframe, so you may need a small height drag — but this is usually cleaner than Option B.

### Option B: Embed by URL (GitHub Pages)

1. Insert → Embed → **By URL** → paste:  
   `https://mohgeis.github.io/Blogger-feed-widget/?blog=https://blog.sudanassociation.se&cols=3&rows=1&compact=1&excerpt=0`  
2. Drag the bottom edge down until the scrollbar disappears → Publish  

Tips for either option:
- Prefer `rows: 1` / `rows=1` on the homepage  
- Use `excerpt=0` (URL) or the HTML snippet (no excerpts) to save height  

Source blog must be public, with **Settings → Site feed** enabled.  

Note: some Google Workspace admins disable custom HTML embeds — if Embed code is missing/blocked, use Option B.
