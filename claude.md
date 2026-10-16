# Ayulyfe landing website

Static marketing site for the AYULYFE Ayurvedic wellness app (ayulyfe.com).
Repository: SergeyGTH/Ayulyfe_landing. No build step, no framework.

## How the site is published
- `main` is the live site. Every push to `main` is published automatically
  by GitHub Pages (Settings -> Pages -> "Deploy from a branch" -> `main`).
  Changes appear on ayulyfe.com about 2 minutes after the push.
- There is no custom GitHub Actions workflow any more. Do not add one.
- Never push directly to `main` unless I explicitly say so. Work on a branch
  and tell me when it is ready for me to merge.

## Files
- `index.html` is the page that is served. Almost all edits go here.
- `ayulyfe-redesign-clean_SO_20260421_04.html` is an old design draft.
  It is NOT served. Do not edit it unless I ask.
- `CNAME` keeps ayulyfe.com attached to the site. NEVER edit, rename or delete it.
- `.gitattributes` and `.github/`: leave alone.

## Things to know about index.html
- There are TWO footers. When changing copyright text or footer content,
  search the whole file (for example for "2025" or "AYULYFE. All rights")
  and update every occurrence.
- Version comment near the top: `<!-- Ver. YYYYMMDD_NN -->`
  (example: `<!-- Ver. 20261014_01 -->`). When I ask for a release or change,
  update it to today's date with the next number for that day.
  It is an HTML comment, so it is invisible in the browser by design.
- The page contains Google Tag Manager / Google Analytics scripts.
  Do not remove or change them unless I ask.
- Download buttons link to the App Store and Google Play. Keep these links
  and the app IDs unchanged unless I give new ones.
- Keep the Account & Data Deletion section and the support@ayulyfe.com contact.

## How to work with me
- I am learning Git and web development. Explain what you are doing in plain
  words and keep changes small.
- Show the change and wait for my OK before committing.
- Use short, clear commit messages, for example "Update footer copyright to 2026".
- Never put passwords, tokens or API keys in any file or commit message.
- Ask before deleting any file.
- To preview: open `index.html` in the browser (`open index.html`).
  Don't start servers or install packages for this project.