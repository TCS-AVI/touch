# Touch: typing software from The Computer Services

Live site: **https://tcs-avi.github.io/touch/**

Touch teaches touch typing from the first key to expert speed, in English and Hindi (Inscript), and lets learners practise for typing tests such as SSC, RRB, JKSSB and the J&K High Court. It is one static page. There is no server, no account, no analytics and no cookies. Everything a learner does is saved only in their own browser.

This repository is separate from the main `tcs-avi.github.io` site, so publishing it does not change anything already on that site.

## What is in this folder

| File | Purpose |
|---|---|
| `index.html` | The whole app (HTML, CSS and JavaScript in one file) |
| `sw.js` | Lets the app work offline after the first visit |
| `manifest.webmanifest`, `icon-192.png`, `icon-512.png`, `favicon.svg` | Install-to-home-screen support and icons |
| `404.html` | Friendly "page not found" page |
| `sitemap.xml` | Optional, for search engines |
| `.nojekyll` | Tells GitHub Pages to serve the files as they are (optional) |
| `README.md` | This file |

## Publish it (about 5 minutes, no command line needed)

1. Sign in to GitHub as **tcs-avi**. The address `tcs-avi.github.io/touch/` only works when the account name is exactly `tcs-avi`.
2. Go to **github.com/new**. Set **Repository name** to exactly `touch`. Choose **Public**. Click **Create repository**.
3. On the new repository page click **uploading an existing file**. Drag in every file from this folder (select them all and drop them in the page), then click **Commit changes**. `index.html` must be at the top level of the repository, not inside another folder.
   - `.nojekyll` is a hidden file and may not appear in your file picker. The site works without it, so skip it if it is awkward.
4. Open **Settings > Pages**. Under **Build and deployment**, set **Source** to **Deploy from a branch**, **Branch** to `main` and the folder to `/ (root)`. Click **Save**.
5. Wait one to two minutes, then open **https://tcs-avi.github.io/touch/**. The Pages settings screen also shows the live link once it is ready.

### Or with git

```bash
git clone https://github.com/tcs-avi/touch.git
cd touch
# copy all files from this folder into it, then:
git add -A
git commit -m "Publish Touch"
git push origin main
```

## Link to it from your main site

Add this line wherever you want a link on `tcs-avi.github.io`:

```html
<a href="/touch/">Free typing practice from The Computer Services</a>
```

## Check it after publishing

- The page opens and asks for a name and goal. Tick the acknowledgement and start.
- Type one stage, then open **My progress & backup** and press Export backup.
- Turn on airplane mode and reload. The app should still open (this works from the second visit).
- On a phone, use the browser menu's **Add to Home screen** or **Install app**.
- Open `https://tcs-avi.github.io/touch/anything` and confirm the 404 page appears.

## Updating the site

- To change the app, edit `index.html` on GitHub (pencil icon) or replace the file, then commit. Visitors get the new version the next time they open it while online.
- If you add, rename or remove files, update the `ASSETS` list in `sw.js` and change `V="touch-v1"` to `touch-v2`, so old copies are replaced.
- **Exam figures need maintenance.** The speeds, durations and error limits live in the `PRESETS` object in `index.html`. They were checked in November 2026. Re-check them against each new recruitment notification, and update the date in the disclaimer when you do.

## Privacy and security notes

- All progress, settings and the practice log are stored in the visitor's browser (`localStorage`, keys starting `tt2:`). Nothing is sent to a server. Raw keystrokes are never saved.
- `index.html` carries a Content Security Policy that tells the browser to refuse any connection to other websites. The only outside request allowed is the Atkinson Hyperlegible font from Google Fonts, which is disclosed in the on-page notice.
- Every project under `tcs-avi.github.io` shares one browser storage area. Touch prefixes its keys with `tt2:`, so it will not clash with your main site or other pages. Its offline service worker only controls the `/touch/` path.
- Search engines read `robots.txt` only from the main domain root, so none is included here. To control indexing, add one to the `tcs-avi.github.io` repository.
- The on-page **Disclaimer & privacy** notice is general information, not legal advice. Have it reviewed for your jurisdiction, and add a contact address if you want one.

## Test locally

```bash
python3 -m http.server 8000
# open http://localhost:8000
```

Offline support needs `http://` or `https://`; opening `index.html` directly from disk works too, without the offline cache.

## Copyright

© The Computer Services. No open-source licence has been added, so all rights are reserved. If you want others to reuse the code, add a `LICENSE` file.
