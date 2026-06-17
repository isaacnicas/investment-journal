# The Journal of Investment Philosophy

A recurring publication distilling lessons from history's greatest investors into practical, usable frameworks. Long-form, design-heavy, released in volumes rather than issues.

**Live site:** https://isaacnicas.github.io/investment-journal/

## Contents

- `index.html` — landing page listing all volumes
- `vol-01.html` — Volume 01: *Hidden in Plain Sight*
- `share-card.png` — 1200×630 social preview image used by the Open Graph / Twitter Card meta tags in every volume

## Publishing a new volume

1. Build the new volume as a single self-contained `.html` file (no external dependencies beyond Google Fonts), named `vol-0X.html`.
2. Update the Open Graph and Twitter meta tags at the top of the file to point to:
   - `og:url` → `https://isaacnicas.github.io/investment-journal/vol-0X.html`
   - `og:image` → reuse `share-card.png`, or generate a new one per volume and reference it by filename
3. Add a new `.issue-card` block to `index.html` linking to the new file, and move the old "Coming soon" placeholder forward.
4. Commit and push to `main`. GitHub Pages redeploys automatically, usually within a minute.

## Deploying this repo on GitHub Pages (one-time setup)

1. Create a new repository on GitHub named `investment-journal` under your account.
2. Push these files to the `main` branch:
   ```
   git init
   git add .
   git commit -m "Volume 01: Hidden in Plain Sight"
   git branch -M main
   git remote add origin https://github.com/isaacnicas/investment-journal.git
   git push -u origin main
   ```
3. On GitHub: go to the repo's **Settings → Pages**. Under "Build and deployment," set Source to **Deploy from a branch**, branch `main`, folder `/ (root)`. Save.
4. Wait a minute or two, then visit `https://isaacnicas.github.io/investment-journal/`.

## After going live

- Run the new URL through [LinkedIn's Post Inspector](https://www.linkedin.com/post-inspector/) and [X's Card Validator](https://cards-dev.twitter.com/validator) once, so each platform fetches and caches the correct preview card instead of a stale or missing one.
- If a custom domain is added later, update all four meta tag URLs (`og:url`, `og:image`, `twitter:image`, plus the same in `index.html`) to match, and add a `CNAME` file with the domain name at the repo root.

## Notes

Each volume is a single static HTML file with inline CSS/JS — no build step, no framework, nothing to install. This keeps every volume permanently viewable by just opening the file, and keeps GitHub Pages deploys instant.
