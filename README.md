# Cosmo Quotes

Quote builder for **Cosmo Tree Services** (lawn care & tree services, Gainesville, FL). Create, save, and print professional client quotes — live at [quote.cosmotreeservices.com](https://quote.cosmotreeservices.com).

## Features

- **Quote builder** — client info, services from an editable catalog, discounts, and a live totals panel
- **Unit-aware pricing** — rates per tree, stump, load, sqft, or hour
- **Monthly recurring services** — e.g. lawn maintenance billed per visit, shown with a `/mo` suffix
- **Per-line add-ons** — wood chipping, crane/heavy equipment, emergency storm response, and more
- **Quote history** — searchable list with status tracking (draft / sent / accepted / declined)
- **Print / Save PDF** — letterhead-style document with the company logo, print-optimized CSS
- **Settings** (PIN-protected) — company info, service & add-on catalogs, quote defaults (including the "How to Pay" section), and PIN management. The default PIN is defined in `index.html`.

## Tech

The entire app is one file: `index.html`. Vanilla HTML/CSS/JS — no framework, no build step, no dependencies.

All data lives in the browser's `localStorage` (`cosmo_settings`, `cosmo_quotes`). Nothing leaves the device, and each domain (production vs. preview) keeps its own independent data.

## Run locally

Open `index.html` directly in a browser, or serve the directory with any static server:

```sh
npx wrangler pages dev .
```

## Deploy

Deploys are direct uploads to the Cloudflare Pages project `cosmo-quotes` (no committed wrangler config, no deploy CI):

```sh
wrangler pages deploy . --project-name cosmo-quotes --branch master
```

- Branch `master` → production, served at `quote.cosmotreeservices.com`
- Any other branch → preview at `https://<branch>.cosmo-quotes.pages.dev`

The `CNAME` file is a leftover from an earlier GitHub Pages setup.

## Repo automation

`.github/workflows/` contains Claude PR-assistant and automated code-review workflows. There is no build or deploy CI.
