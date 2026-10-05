# iOS Team Q3 Report

A single-page report of the iOS team's Q3 2026 delivery: releases, project timelines, build history, tools built beyond releases, learnings and the Q4 plan.

## Putting it online with GitHub Pages

1. Create a new repository on GitHub, for example `Q3iOSReport`.
2. Upload `index.html` to the root of the repository (keep the file name `index.html`).
3. Open **Settings → Pages**.
4. Under **Build and deployment**, set **Source** to *Deploy from a branch*, choose branch `main` and folder `/ (root)`, then press **Save**.
5. Wait about a minute. The page appears at `https://<your-username>.github.io/<repository-name>/`.

To update the report later, replace `index.html` and commit. The site refreshes automatically.

## App icons

Each app looks for its icon in this order:

1. `icons/<name>.png` in this repository
2. `icons/<name>.jpg`
3. Apple's iTunes Lookup API, fetched when the page loads
4. A coloured tile with the app's first letter

Putting the images in an `icons/` folder is the reliable option: it needs no internet
access and cannot be blocked. Create a folder called `icons` next to `index.html` and
add square PNGs (256px is plenty) named exactly:

```
fasting.png        fmradio.png      adblocker.png    authenticator.png
cleaner.png        upkee.png        resumeit.png     translate.png
dietplan.png       printer.png      locateus.png     cleanpath.png
captions.png       menufit.png      pbpred.png       soberly.png
purecheck.png      caloric.png      pdfeditor.png
```

Any name you leave out simply falls back to the API, then to a letter tile, so you can
add them a few at a time.

## Editing the content

Everything is in `index.html`. The project data sits near the bottom in the `<script>` block:

- `GROUPS` — the status groups and their colours
- `P` — every project: owners, targets, builds, timeline, scope and outcome
- `QA` — the incremental-testing build history per project
- `APPID` — App Store IDs used to fetch icons
