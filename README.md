# ActTrader Trader User Manual (with how-to videos)

This repository is the **finished website**: plain HTML, CSS, JavaScript, images and MP4 videos.
There is no server code, database or build step. Search works in the browser.

**Live address:** https://help.acttrader.com/v2/
Preview copy: https://rakesh-kumar9.github.io/trader-manual/

## Install on help.acttrader.com/v2

1. Get the files: **Code → Download ZIP** on GitHub (or `git clone`), or use the archive
   `ActTrader-Trader-Manual-v2.zip` (its files are already at the top level).
2. Copy everything **except `.git`, `.nojekyll` and `README.md`** into the folder served at
   `https://help.acttrader.com/v2/`, so that `index.html` sits directly in that folder.
3. Open https://help.acttrader.com/v2/ and check a page and a video.

The manual is built for `/v2/`:
- All links between pages, images and videos are **relative**, so they work in that folder.
- The sitemap and each page's canonical address use `https://help.acttrader.com/v2/`.
- The page-not-found page (`404.html`) is self-contained: it works in any folder and offers
  search, the manual home and the video list. To use it, set it as the error page for the
  `/v2/` folder (IIS: Error Pages → 404 → `/v2/404.html`; nginx: `error_page 404 /v2/404.html;`;
  Apache: `ErrorDocument 404 /v2/404.html`). Without this the server shows its own error page;
  everything else works either way.

## Server settings

- Size is about 210 MB, mostly the videos in `videos/`.
- MIME types: `.mp4` → `video/mp4`, `.srt` → `text/plain`, `.js` → `text/javascript`,
  `.json` → `application/json`, `.svg` → `image/svg+xml`.
  IIS may not serve `.srt` until a MIME type is added for it.
- Allow **range requests** for `.mp4` (on by default in IIS, nginx and Apache) so viewers can
  jump inside a video.
- No rewrite rules, no server-side code, no database.

## Updating later

The manual team rebuilds the site and pushes it here. To update the server, download again and
replace the folder contents.
