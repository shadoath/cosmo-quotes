# Cosmo Quotes

Quote builder for **Cosmo Tree Services** (lawn care & tree services, Gainesville, FL). Create, save, and print professional client quotes — live at [cosmo-quotes.pages.dev](https://cosmo-quotes.pages.dev). The intended production domain is `quote.cosmotreeservices.com` (DNS / custom-domain attachment still pending).

## Features

- **Quote builder** — client info, services from an editable catalog, discounts, and a live totals panel
- **Unit-aware pricing** — rates per tree, stump, hour, visit, load, sqft, lnft, or each
- **Monthly recurring services** — e.g. lawn maintenance billed per visit, shown with a `/mo` suffix
- **Per-line add-ons** — wood chipping, crane/heavy equipment, emergency storm response, and more
- **Quote history** — searchable list with status tracking (draft / sent / accepted / declined)
- **Print / Save PDF** — letterhead-style document with the company logo, print-optimized CSS
- **Settings** (PIN-protected) — company info, service & add-on catalogs, quote defaults (including the "How to Pay" section), and PIN management. The default PIN is defined in `index.html`.

## Tech

The entire app is one file: `index.html`. Vanilla HTML/CSS/JS — no framework, no build step. The only external dependency is Google Fonts, loaded at runtime.

Quote data never leaves the browser: everything is stored in `localStorage` (`cosmo_settings`, `cosmo_quotes`), per browser and per origin — quotes saved on one domain or preview URL won't appear on any other.

## Run locally

Open `index.html` directly in a browser, or serve the directory with any static server:

```sh
npx wrangler pages dev .
```

## Deploy

Deploys are direct uploads to the Cloudflare Pages project `cosmo-quotes`. Stage `index.html` alone so repo files (README, docs) aren't published to the site:

```sh
mkdir -p dist && cp index.html dist/
wrangler pages deploy dist --project-name cosmo-quotes --branch master
```

You must be authenticated against the Cloudflare account that owns the project — if your wrangler login can see multiple accounts, set `CLOUDFLARE_ACCOUNT_ID` to pick the right one.

- Branch `master` → production
- Any other branch → a preview at `https://<branch>.cosmo-quotes.pages.dev`, where `<branch>` is the sanitized branch name (lowercased, `/` and other non-alphanumerics become `-`; e.g. `chore/add-readme` → `chore-add-readme.cosmo-quotes.pages.dev`)

## Repo automation

GitHub Actions workflows in `.github/workflows/` include a Claude PR assistant and automated code review.
