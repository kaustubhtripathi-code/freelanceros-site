# HANDOVER — freelanceros-site

Marketing site for **FreelancerOS** (the suite at `OneDrive\Desktop\freelanceros` — read its
CLAUDE.md, and `C:\dev\freelancer-suite\HANDOVER.md` for the other instance). Self-contained
`index.html` + `promo.mp4`, click-to-enlarge screenshot lightbox.

- Repo: `kaustubhtripathi-code/freelanceros-site` · GitHub Pages
  (https://kaustubhtripathi-code.github.io/freelanceros-site/), `.nojekyll` present.
- Redeploy = push to default branch.
- Keep pricing/module claims downstream of the product repos; re-shoot screenshots after
  major UI changes.
- User steps: none pending.

Last audit: 2026-07-12 (state = last commit `163e3e3`, 2026-07-07).

## 2026-07-25 responsive + CTA pass
Site had **zero media queries** and overflowed horizontally at 375px (391px scrollWidth,
caused by the header wordmark + two ghost buttons). Added a `@media(max-width:720px)` block
(tighter buttons, stacked calculator total, wrapping cost rows, single-column screenshots)
plus a `@media(max-width:400px)` header wrap. Verified 0 overflow at 360 / 375 / 820 / 1280.
The three pricing CTAs were `href="#"` (dead) — now `mailto:kaustubh.trt@gmail.com` with
per-plan subjects, matching shelfscore-site's pattern. FreelancerOS is not self-serve for
strangers, so mail is the honest destination; swap to a signup URL when one exists.
Footer now carries the contact email + an "An Everfold Labs product" link.
