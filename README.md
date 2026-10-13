# ActTrader Trader User Manual (with how-to videos)

This repository is the **finished website**: plain HTML, CSS, JavaScript, images and MP4 videos.
There is no server code, database or build step. Search works in the browser.

Live preview: https://rakesh-kumar9.github.io/trader-manual/

## Putting it on our own domain (for the server team)

1. Get the files: `git clone https://github.com/rakesh-kumar9/trader-manual.git`
   (or on GitHub: **Code → Download ZIP**, then extract).
2. Copy **everything** in this folder (except `.git` and this `README.md`) to the web server,
   either at the root of a site or in a sub-folder such as `/v2/`.
   All links are relative, so any folder works. The old manual does not need to be removed.
3. Open `index.html` in that folder, for example `https://help.example.com/v2/`.

Server notes:
- Size is about 210 MB, mostly the videos in `videos/`.
- `.mp4` must be served as `video/mp4`, and `.srt` as `text/plain`.
  Range requests (normal on IIS, nginx and Apache) let viewers skip through videos.
- No special rewrite rules are needed. `404.html` can be used as the not-found page.

## Updating

The manual team rebuilds the site and pushes it here. To update the server, download again
and replace the folder contents.
