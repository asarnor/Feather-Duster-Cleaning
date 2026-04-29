# Feather Duster Cleaning

Marketing site for Feather Duster Cleaning — commercial, residential, and event cleaning across Los Angeles, the Inland Empire, and Orange County.

This is a single-page static site (one `index.html` with embedded CSS/JS, plus image assets). No build step is required.

## Local preview

```bash
npm run dev
# or simply
npx serve .
```

Then open http://localhost:3000.

## Deploying to Vercel

The site is configured as a static deployment. Two ways to deploy:

### Option A — GitHub import (recommended)

1. Push the repo to GitHub.
2. Go to https://vercel.com/new and import the repository.
3. Framework preset: **Other** (auto-detected as a static site).
4. Build & Output settings — leave defaults blank:
   - Build Command: *(leave empty)*
   - Output Directory: *(leave empty — root is served)*
   - Install Command: *(leave empty)*
5. Click **Deploy**.

### Option B — Vercel CLI

```bash
npm i -g vercel
vercel        # preview deploy
vercel --prod # production deploy
```

### Custom domain

After the first deploy, in **Project → Settings → Domains** add `featherdustercleaning.com` and `www.featherdustercleaning.com`. Update DNS at your registrar with the records Vercel shows. The site is configured to canonicalize on `https://www.featherdustercleaning.com/` — if you use a different host, update:

- `<link rel="canonical">` and Open Graph URLs in `index.html`
- `sitemap.xml` and `robots.txt`

## File map

```
index.html        Single-page site (HTML + inline CSS/JS)
404.html          Custom not-found page (Vercel serves this automatically)
vercel.json       Headers (security + cache) and clean URLs
sitemap.xml       SEO sitemap
robots.txt        Crawler directives
package.json      Local dev script only (no build)
assets/           Logos, banner, headshot
```

## Improvement backlog

- Compress `assets/jim-headshot.png` (~2.4 MB) with TinyPNG/Squoosh and add a WebP/AVIF variant served via `<picture>` for faster mobile loads.
- Add a Google Business Profile reviews widget if you want live ratings.
- Wire a real contact form (Vercel Forms, Formspree, Resend, etc.) once you want lead-capture beyond the mailto/sms links.
- Add a privacy & terms page if you start collecting form data.
