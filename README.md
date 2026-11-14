# SUDUMANN Downloads

Official download page for SUDUMANN games and apps, served with GitHub Pages:
**https://sudumann.github.io/Downloads/**

It's a single static page (`index.html`) with no build step, frameworks or web fonts, so it loads fast on any phone.

## Turn on GitHub Pages

Repository **Settings → Pages → Build and deployment → Deploy from a branch → `main` / `(root)`**.

## Adding a download

1. Put the file in `downloads/` (for example `downloads/OGFlac.apk`).
2. In `index.html`, find the app's card and fill in the empty `href=""` on its button:

   ```html
   <a class="btn btn-primary" href="downloads/OGFlac.apk" download data-dl>…Android<span class="soon">Soon</span></a>
   ```

   A button with an empty `href` shows as greyed-out **Soon**. Once it has a link, it becomes a normal download button automatically.
3. Add the file's size and SHA-256 to the **Verify your download** table near the bottom of `index.html`:

   ```
   certutil -hashfile downloads\OGFlac.apk SHA256
   ```

GitHub blocks single files over 100 MB. For bigger installers (for example a Windows `.exe`), upload the file to a **GitHub Release** and link to its download URL instead.

## Other links

- **YouTube:** paste your channel URL into the two `href=""` links marked `data-optional` (the Google Play notice and the footer). They stay hidden until they have a URL.
- **Google Play:** when a listing goes live, replace that card's "Google Play listing coming soon" line with a link to the listing.

## Files

```
index.html                 the page (styles and the small script are inline)
favicon.svg, apple-touch-icon.png
assets/brand/sudumann.svg  wordmark
assets/img/                card covers, app icons, social preview (og.jpg)
downloads/                 APK / EXE files
```
