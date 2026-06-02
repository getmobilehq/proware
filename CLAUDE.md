# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

Proware Associates marketing site — persistent project context. Read this fully before making
changes. For the task list and launch steps, see `HANDOVER.md`.

## Project

Marketing website for **Proware Associates**, a fully registered cargo & logistics company
(UK + international). It is a single-page static site. The brand differentiator vs. typical
couriers: Proware also offers **Leasing** and **Warehouse Management**, summarised as
**"Move it · Lease it · Store it."**

- **Type:** static site, **no build step** — plain HTML/CSS/JS in one file (`index.html`).
- **Preview:** open `index.html` in a browser, or run `npx serve` / `python3 -m http.server`.
- **Audience:** businesses and individuals shipping, leasing or storing goods.
- **Status:** v1 approved by client; finishing for launch + first GitHub push.

## Structure

```
index.html        # the entire site (HTML + inline CSS + inline JS)
brand/            # reference only — not part of the deployed site
  Proware-Brand-Bible.pdf       # canonical visual brand reference
  proware-brand-bible.html
  Proware-Website-Copy.docx     # all site copy + "what we need from Proware" list
CLAUDE.md  README.md  HANDOVER.md
```

If you split `index.html` into `css/` and `js/`, update this file and `README.md` to match.

## Brand tokens (must match the brand bible exactly)

Colours (CSS variables already defined in `index.html`):
- Ink `#0C1E27` (primary text, dark sections, logo) · Ink Soft `#16323F` (secondary dark, hovers)
- Signal Amber `#EE6A1C` (accent/CTAs) · Amber Deep `#CE530E` (hover/pressed)
- Paper `#F6F3EC` (primary bg) · Paper Tint `#EDE7DB` (alt bg) · Slate `#5A6A71` (muted text)

Type (Google Fonts):
- **Bricolage Grotesque** 600–800 — display/headings (tight tracking)
- **Manrope** 400–700 — body & UI
- **Space Mono** 400/700 — eyebrow labels, indices, metadata (uppercase, wide tracking)

Signatures: thin 1px grid motif, pill buttons (100px radius), 14px card corners,
dark inverted sections for emphasis, generous whitespace.

## Voice

Plain-spoken, confident, concrete; "partner, not courier." Active voice. Avoid hype.

## Immutable rules

1. **No invented metrics.** Proware is newly registered — never add fake stats, client counts,
   or "years in business" numbers. Use capability statements until real figures are supplied.
2. **Amber stays rare.** It signals "act here." Don't spread it across the UI.
3. **Stay minimalist.** Don't add decoration, libraries, or sections that aren't earning their place.
4. **Keep it dependency-light.** No framework or build tooling unless explicitly requested; vanilla
   HTML/CSS/JS. Any animation must respect `prefers-reduced-motion`.
5. **Copy is canonical in `brand/Proware-Website-Copy.docx`.** Match it; flag any rewrite.

## Services (order on page)

01 Air Freight · 02 Sea Freight · 03 Road & Door-to-Door · 04 **Leasing** (edge) ·
05 **Warehouse Management** (edge) · 06 Customs & Packaging.

Leasing scope is **confirmed: warehouse space + vehicles + handling equipment** (rent capacity you
run yourself). Warehouse Management is the *managed* service (we run it). Keep that contrast clear.

## Open decisions (confirm with the owner before resolving)

- **Tracking:** the reference brand features parcel tracking; this site currently omits it. Decide
  whether to add a tracking section/nav item.
- **Contact form:** currently shows a client-side confirmation only — needs wiring to a real handler.
- **Logo:** the inline SVG monogram is a working placeholder; swap if real artwork exists.

## Placeholders awaiting real content (do not invent — leave flagged until supplied)

Phone · email · office address · opening hours · company registration number. All appear in the
Contact section and footer of `index.html`. Full list: `brand/Proware-Website-Copy.docx` §9.
