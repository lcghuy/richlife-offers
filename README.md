# RichLife Offers

Standalone static landing pages, deliberately separate from the
Journey app (which is pinned to basePath "/journey" and can't serve
anything outside it — see the Journey repo's next.config.ts).

richlife.community/offer/* proxies here via a rewrite in the Journey
app's next.config.ts, so the URL bar always shows
richlife.community/offer/<slug> no matter what this project's own
Vercel URL is.

## Adding a new offer page

Drop a new `<slug>.html` file at the root of this repo and push. Once
deployed, it is live at `richlife.community/offer/<slug>` immediately
-- no change needed in the Journey repo, since the rewrite there
forwards the whole `/offer/*` path space here.

`vercel.json`'s `cleanUrls: true` is what makes `/<slug>` resolve to
`<slug>.html` without the extension.
