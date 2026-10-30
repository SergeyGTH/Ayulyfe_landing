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
- `images/` holds the founders' photos used in the Experts section
  (`dr-sreelal-sankar` and `poornima-mukkanniyil`, each as .webp and .jpg).
  Keep the file names: index.html and its structured data point to them.
- `og-image.jpg` (1200x630 share card), `icon.png` (512x512 app icon) and
  `app-screenshot.png` (App Store frame 1) sit in the repo root next to
  index.html. They are not shown on the page: social apps use og-image.jpg
  for link previews, and Google uses icon.png and app-screenshot.png from
  the structured data. Keep the names and keep them in the root. If one is
  replaced, keep the same size.
- `get/index.html` is a small redirect page at ayulyfe.com/get/. The QR code
  in the download block points to it. It sends Android phones to Google Play,
  iPhones/iPads to the App Store and computers to the download block on the
  home page. It is hidden from Google (noindex). It can also be used as one
  short "get the app" link in emails or print. Do not rename or move the
  folder: the QR code has this address built in.
- `ayulyfe-redesign-clean_SO_20260421_04.html` is an old design draft.
  It is NOT served. Do not edit it unless I ask.
- `CNAME` keeps ayulyfe.com attached to the site. NEVER edit, rename or delete it.
- `.gitattributes` and `.github/`: leave alone.

## Things to know about index.html
- There are TWO footers. When changing copyright text or footer content,
  search the whole file (for example for "2025" or "AYULYFE. All rights")
  and update every occurrence.
- Version comment on the first line: `<!-- Ver. YYYYMMDD_NN -->`
  (example: `<!-- Ver. 20261014_01 -->`). When I ask for a release or change,
  update it to today's date with the next number for that day.
  It is an HTML comment, so it is invisible in the browser by design.
- Every HTML page has its own version line (`index.html`, `get/index.html`).
  Update only the version of the file you change; each file counts its own
  numbers. Both files are called index.html, so check the first line to
  tell them apart.
- The page contains Google Analytics (gtag) scripts, ID G-PBYEY4NG2T.
  `get/index.html` has the same tag. Do not remove or change them unless I ask.
- Download buttons link to the App Store and Google Play. Keep these links
  and the app IDs unchanged unless I give new ones. If they change, update
  them in both `index.html` and `get/index.html`.
- Smart download buttons: in-page buttons marked `data-get-app` keep the App
  Store link in the HTML, and a script at the end of the page sends Android
  to Google Play and makes computers scroll to the download block. A new
  general download button should get `data-get-app` too. Buttons that name
  a store (App Store / Google Play) do not get it.
- GA4 events from these: `get_app_click` (button clicks) and `qr_get_app`
  (QR scans on /get/).
- The founders appear in three places: the Team section (id "experts", menu
  label "Team"), the Organization structured data (`founder`) and the FAQ
  "Who created AYULYFE?" (visible and in the FAQ structured data). Keep them in
  sync when bios change.
- AYULYFE was founded by four people: Natalia Barsegiyan (business), Sergey
  Orlov (technology) and two Ayurvedic physicians. Never write that AYULYFE was
  founded by the physicians alone. Only the two physicians have cards.
- Names of the physicians: never use "Dr." (BAMS is not a doctorate outside
  India, and NAMA says BAMS holders must not call themselves "doctor" in the
  US). Use "Vaidya Sreelal Sankar" and "Vaidya Poornima Sreelal (Mukkanniyil)",
  with BAMS as the qualification.
- NAMA badge: `images/nama-organizational-member-2026.*` (Organizational
  Member). The badge shows the year. Membership currently expires 17 Apr 2027;
  after each renewal download the new year's badge from the NAMA members area
  (2026 Member Badges -> Organizational Member Badge), replace both files and
  update the file names and alt text. Remove the badge if membership lapses.
- Tone about medicine: Ayurveda complements modern medicine, never criticise
  or compete with it, and never make treatment or cure claims.
- Keep the Account & Data Deletion section and the support@ayulyfe.com contact.

## Mobile and tablet (keep the site adaptive)
- Every change to index.html must work on phones and tablets, not only on a
  computer. Before showing a change, check it at 360px and 390px (phones),
  768px (tablet) and a desktop width:
  - no sideways scrolling (the page must not be wider than the screen);
  - the menu button (top right, under 960px) opens and closes and its links work;
  - text is readable (no text under 12px except the small uppercase labels)
    and nothing is cut off at the screen edges;
  - buttons and links are easy to tap (about 44px high on phones).
- Layout switches: 960px (tablet and phone: one column, menu button) and
  600px (phones: smaller spacing, smaller Agni circle). Put new mobile rules in
  the "MOBILE & TABLET" block at the end of the styles.
- Avoid fixed widths wider than about 320px; use max-width or percentages.
- The FAQ opens one answer at a time on tap. New FAQ entries keep the same
  structure (question in `itemprop="name"`, answer in `itemprop="acceptedAnswer"`)
  and are added to the FAQ structured data too.

## How to work with me
- I am learning Git and web development. Explain what you are doing in plain
  words and keep changes small.
- Show the change and wait for my OK before committing.
- Use short, clear commit messages, for example "Update footer copyright to 2026".
- Never put passwords, tokens or API keys in any file or commit message.
- Ask before deleting any file.
- To preview: open `index.html` in the browser (`open index.html`).
  Don't start servers or install packages for this project.