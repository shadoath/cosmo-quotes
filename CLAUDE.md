# CLAUDE.md

Single-page quote builder for Cosmo Tree Services. The entire app is one file: `index.html` — all HTML, CSS, and JavaScript inline. There is no build step, no framework, and no package manager. Keep it that way: make changes by editing `index.html` only, and do not add dependencies, build tooling, or new source files.

## Who files issues here

The site owner is non-technical. Issues arrive as plain-English requests (often via `@claude`). Interpret them charitably, keep the change minimal, and write PR titles/descriptions in simple, non-technical language — say what changed on the site, not how the code changed.

## Constraints

- **Data lives in localStorage** under `cosmo_settings` and `cosmo_quotes`. Never rename these keys or change stored shapes in ways that break existing saved data; migrate defensively if a shape must change.
- **Settings are PIN-gated** in the app. Don't remove or weaken the PIN gate, and never print the PIN in docs, comments, or PR text.
- **Mobile first**: the owner uses this on a phone in the field. Verify layouts work at narrow widths.
- Don't modify `.github/workflows/` or `HANDOFF.md` unless the request explicitly asks for it.

## Deploys

Merging to `master` auto-deploys to production (Cloudflare Pages, `quote.cosmotreeservices.com` / `cosmo-quotes.pages.dev`). Every PR from a branch in this repo gets a preview deploy; a bot comment on the PR links to it (fork PRs are skipped — they can't access deploy secrets). No manual deploy steps are needed in PRs.

When you finish work on an issue, you cannot open the PR yourself — the owner clicks the create-PR link in your reply. Put that link where it can't be missed and tell him, in plain words, to click it and then press the green "Create pull request" button.

## Testing

Open `index.html` directly in a browser. There is no test suite.
