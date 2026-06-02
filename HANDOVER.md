# Handover — Proware Associates website

This briefs **Claude Code** to finish the site and push it to GitHub. Read `CLAUDE.md` first
(Claude Code loads it automatically at session start). Confirm the three "Open decisions" and
gather the placeholder content from the owner before treating the site as launch-ready.

---

## Kickoff prompt (paste this as your first message to Claude Code)

> Read CLAUDE.md and HANDOVER.md. This is a finished-v1 static marketing site in `index.html`.
> Work through the "Definition of done" checklist below in order. Pause and ask me about the
> three Open decisions and the placeholder content before changing those. When the working tree
> is clean and you've confirmed with me, initialise git and push to a new GitHub repo following
> the "Git & GitHub" steps. Don't invent any business facts or metrics.

---

## Current state

- `index.html` — complete, responsive, single-file site (inline CSS + JS). Sections: hero,
  services (6), why Proware, how-it-works, about, contact/quote form, footer.
- Contact form validates client-side and shows an inline confirmation; **not yet wired** to send.
- Brand references in `brand/`. v1 design signed off by the client.

## Definition of done

### A. Content & brand
- [ ] Replace placeholders with real values (phone, email, office address, hours, company reg. no.).
- [ ] Decide the **Tracking** question; add a section + nav item if yes.
- [ ] Wire the **contact form** to a real handler (see options below); keep the inline success state.
- [ ] Swap the placeholder logo for final artwork **if available**, and generate a favicon set
      (`favicon.ico`, `apple-touch-icon.png`, `site.webmanifest`).

### B. Engineering
- [ ] (Optional, recommended) Split `index.html` into `index.html` + `css/styles.css` + `js/main.js`
      for maintainability; update `CLAUDE.md` + `README.md` if you do.
- [ ] SEO/meta: keep `<title>` + description; add Open Graph + Twitter Card tags, a canonical URL,
      `robots.txt` and `sitemap.xml`.
- [ ] Accessibility: verify heading order and landmarks, visible focus states, colour contrast
      (check amber on ink and muted text), `aria-label`s on icon-only controls, and that the
      scroll-reveal animations are gated behind `prefers-reduced-motion`.
- [ ] Performance: confirm font `preconnect` + `display=swap`, lazy-load any future images, and
      run Lighthouse (target 90+ across the board).
- [ ] Add a `LICENSE` (or mark the repo private) and a short footer copyright once confirmed.

### C. QA
- [ ] Responsive check at ~360 / 768 / 1024 / 1440 px, incl. the mobile menu and the form.
- [ ] Cross-browser smoke test (Chromium, Firefox, Safari/WebKit).
- [ ] Validate HTML; no console errors.

## Contact form options (pick one with the owner)
- **Formspree / Web3Forms** — drop-in `action` endpoint, no backend. Fastest.
- **Netlify Forms** — add `data-netlify="true"`; works if hosting on Netlify.
- **mailto fallback** — simplest, but opens the user's mail client (lower conversion).

## Deploy options (static)
- **GitHub Pages** — enable Pages on the repo (Settings → Pages → deploy from branch / Actions). Free, fits GitHub.
- **Netlify / Vercel / Cloudflare Pages** — connect the repo for auto-deploy on push + previews.

---

## Git & GitHub

> These run on the owner's machine with the owner's GitHub credentials. Creating the repo and the
> first push are irreversible/account actions — **confirm with the owner before running them.**
> Requires the GitHub CLI authenticated (`gh auth status`; if not, `gh auth login`) or an SSH remote.

```bash
# from the project root
git init
git add .
git commit -m "Proware Associates marketing site — v1"
git branch -M main

# Option 1 — GitHub CLI (creates the repo and pushes)
gh repo create proware-website --private --source=. --remote=origin --push
# use --public instead of --private if the owner wants it public

# Option 2 — manual remote (repo already created on github.com)
# git remote add origin git@github.com:<owner>/proware-website.git
# git push -u origin main
```

After the first push, set up the chosen deploy (e.g. enable GitHub Pages) and add the live URL
to `README.md`.

## Suggested commit sequence
1. `chore: project scaffold, CLAUDE.md and handover docs`
2. `feat: real contact details and form handler`
3. `feat: SEO meta, Open Graph, favicon`
4. `a11y/perf: contrast, focus states, reduced-motion, Lighthouse fixes`
5. `docs: update README with live URL`
