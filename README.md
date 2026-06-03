# Proware Associates — Marketing Website

Single-page marketing site for **Proware Associates**, a cargo & logistics company offering
freight (air / sea / road), **leasing**, and **managed warehousing** — *move it, lease it, store it.*

Static site, no build step. Vanilla HTML/CSS/JS.

**Live:**
- https://prowareweb.netlify.app — Netlify
- https://getmobilehq.github.io/proware/ — GitHub Pages (from `main`, root)

Both deploy from `main`; every push redeploys.

## Run locally

```bash
# any static server, e.g.
npx serve .
# or
python3 -m http.server 8000
```

Then open the printed URL. Or just open `index.html` directly in a browser.

## Structure

```
index.html   # the full site (inline CSS + JS)
brand/       # brand bible (PDF/HTML) + website copy doc — reference, not deployed
CLAUDE.md    # project context for Claude Code
HANDOVER.md  # finishing checklist + GitHub/deploy steps
```

## Status

v1 design approved. Remaining work to launch (real contact details, form wiring, SEO, a11y,
deploy) is tracked in **HANDOVER.md**.

## Brand

Colours, type and usage are defined in `brand/Proware-Brand-Bible.pdf`. All site copy lives in
`brand/Proware-Website-Copy.docx`.
