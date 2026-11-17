# Future Justice System website

Astro (Node.js) static site for futurejusticesystem.com. Deployed to GitHub Pages by `.github/workflows/deploy.yml` on every push to `main`.

## Where things live
- Text, dates, contact details, social links: `src/data/site.json`
- Panels and panelists: `src/data/panels.json`
- Founder and team members: `src/data/team.json`
- Gallery photos: `src/data/gallery.json` (images in `public/images/gallery/`)
- Team photos: `public/images/team/`
- Pages: `src/pages/*.astro` · Shared parts: `src/components/` · Design: `src/styles/global.css`

## Brand rules (keep these)
- Colours: navy #0E1C41, off-white #F4F5F8, gold gradient #ECD196 → #C9A15B → #A47A3A. Use the CSS variables in `global.css`.
- Font: Sora only.
- Style: large rounded panels, glass cards on navy, gold icon tiles, stroke icons from `src/components/Icon.astro`. No emoji.
- Keep text short and use icons where possible.
- Never use em dashes in site copy.
- Must stay mobile responsive: check at 390px width.

## Workflow
- Prefer editing the JSON data files over editing page markup.
- New photos: convert to .webp, max 1600px wide, put in `public/images/...`.
- After changes run `npm run build` and make sure it passes before committing.
