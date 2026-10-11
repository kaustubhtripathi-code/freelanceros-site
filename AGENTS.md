# AGENTS.md — freelanceros-site

**PUBLIC repo.** Static marketing page for FreelancerOS, served by GitHub Pages at
https://kaustubhtripathi-code.github.io/freelanceros-site/. Active. The product it markets is the
canonical `freelancer-suite` repo (the older `freelanceros` top-level app is a frozen prototype).

## Stack & layout
- Self-contained `index.html` (inline CSS/JS, live stack-cost calculator, screenshot lightbox),
  `promo.mp4`, `screenshots/*.png`, `assets/og-image.png`, `.nojekyll`. No build step, no dependencies.
- `ci/site_check.py` — offline check: every local `src`/`href`/`poster` resolves to a tracked file,
  inline JS parses (needs `node`), and stages publishable files into `_site/`.

## Setup / run / test
```bash
python3 ci/site_check.py --repo freelanceros-site   # (verified 2026-10-11) then: rm -rf _site
python3 -m http.server 8000                         # preview at http://localhost:8000 (unverified)
```
CI (`.github/workflows/ci-cd.yml`) runs the same check; on `main` only, it deploys `_site/` to Pages.
Branch/PR runs never deploy. **Merging to `main` = publishing to the public internet.**

## Environment variables
None required.

## Codex cloud environment
- Setup script: none needed (Python 3 + Node are present in the default image).
- Internet during agent phase: off is fine.
- Secrets to add: none.

## Rules for agents
- Everything committed here is public: no secrets, internal notes, private repo names/paths,
  customer data, or unreleased pricing.
- Keep pricing/module claims downstream of `freelancer-suite`; re-shoot screenshots after major UI changes.
- Contact email is the plain address already in the page — never use `+alias` variants.
  Pricing CTAs are `mailto:` on purpose (not self-serve yet); swap to a signup URL only when one exists.
- Keep it mobile-safe: no horizontal overflow at 360/375/820/1280px (`@media(max-width:720px)` and
  `(max-width:400px)` blocks exist for this).
- Only reference assets that are tracked in git (the CI check fails otherwise). `_site/` is a build
  output — do not commit it.

## Open work
- Branch `ci/portfolio-20260907` is identical to `main` (nothing unmerged).
- No signup flow yet; CTAs remain mailto.
