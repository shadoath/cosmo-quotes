# How to Update Your Website

This is the quote builder for Cosmo Tree Services. Always use it at one address: **quote.cosmotreeservices.com** — bookmark it. Your prices, settings, and saved quotes are stored under the address you use, so sticking to the bookmark keeps everything in one place.

There are two ways to change it, depending on what you need.

## 1. Changing prices, services, or payment info

You don't need anything below for this. Open the website, tap the **settings** (gear) icon, and enter the settings PIN (Skylar gave this to you). You can edit prices, service names, and payment details right there. Changes save on your device immediately.

## 2. Changing anything else (layout, new features, wording, colors...)

You describe what you want in plain English, and an AI assistant makes the change for you. You review it before it goes live.

### Step by step

1. Go to the project page on GitHub — **github.com/shadoath/cosmo-quotes** — and click the **Issues** tab, then the green **New issue** button.
2. Give it a short title, and in the description write what you want changed — in your own words — and include the text `@claude` anywhere in it. For example:

   > @claude Make the "Add Service" button bigger and easier to tap on a phone.

3. Wait a few minutes. Claude (the AI) will reply on your issue with what it changed and a **link to create a pull request** — a proposed change waiting for your approval. Click that link, then press the green **Create pull request** button on the page that opens.
4. On the pull request page, wait for the **"Preview this change"** comment (a minute or two), then click its link. That's a separate test copy of the site with the change applied — check it on your phone or computer. The test copy shows example data, not your real prices or saved quotes, so judge the change itself, not the numbers.
5. Happy with it? Press the green **Merge pull request** button (then **Confirm merge**). The real website updates about a minute later.
6. Not happy? Reply on the pull request with what to fix and include `@claude` again — for example: *"@claude make the button green instead."* When the fix is ready, a fresh **"Preview this change"** comment appears (you'll get an email), with a link to the updated preview.

### Things to know

- Nothing goes live until **you** press Merge. Looking at previews is always safe.
- An automatic reviewer also checks every change for mistakes and leaves notes.
- Your saved quotes and settings live in your own browser — website updates never erase them.
- Preview links aren't secret-proof: anyone you send one to can open it. Fine for showing a change to someone, just don't treat previews as hidden.

## If something breaks or you get stuck

Contact Skylar. Hosting, the AI assistant, and the domain plumbing are managed for you under your maintenance arrangement.

---

## One-time setup checklist (Skylar)

Everything above only works once these are done:

- [ ] `CLOUDFLARE_API_TOKEN` repo secret set (Pages Write, whiteboardworks account); `CLOUDFLARE_ACCOUNT_ID` is already set.
- [ ] Owner's GitHub account invited as a collaborator with write access — required both for `@claude` to respond to him and for the Merge button to appear.
- [ ] `quote.cosmotreeservices.com` attached as a custom domain on the `cosmo-quotes` Pages project, and the owner's DNS host has a CNAME `quote` → `cosmo-quotes.pages.dev`.
- [ ] Owner bookmarks `quote.cosmotreeservices.com` and uses only that address from day one — app data is stored per-address (localStorage), so anything he sets up on `cosmo-quotes.pages.dev` will not follow him to the custom domain.
- [ ] Settings PIN handed to the owner privately (never write it in this repo — it's public).
