# Hanees Hazli — Portfolio

A single-file personal portfolio site. Everything (markup, styles, scripts, assets) is
bundled into `index.html`, so there is no build step and no dependencies.

## Viewing it locally

Open `index.html` in a browser, or serve it:

```
python3 -m http.server 8000
```

Then visit http://localhost:8000

## Publishing with GitHub Pages

In this repository: **Settings → Pages → Source: Deploy from a branch → `main` / `root`**.
The site will be live at `https://<username>.github.io/hanees-hazli-portfolio/`.

## Notes

- `index.html` is a generated bundle (~3.3 MB). Edit it at the source that produced it
  and re-export, rather than hand-editing the bundled file.
- Video embeds are loaded from Vimeo at runtime and require an internet connection.
