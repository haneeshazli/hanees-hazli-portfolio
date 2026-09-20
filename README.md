# Hanees Hazli — Portfolio

Personal portfolio site, live at **https://hanees.site**

A single file: markup, styles, scripts and assets are all bundled into
`index.html`, so there is no build step and no dependencies.

## Viewing it locally

Open `index.html` in a browser, or serve it:

```
python3 -m http.server 8000
```

Then visit http://localhost:8000

## How it's deployed

| Layer | Provider |
|---|---|
| Hosting | GitHub Pages (`main` branch, root) |
| DNS | Cloudflare (`sullivan` / `tani.ns.cloudflare.com`) |
| Registration | GoDaddy |
| TLS | Let's Encrypt, issued automatically by GitHub |

`hanees.site` resolves to GitHub Pages' four A records. The A records are
set to **DNS only** (not proxied) so GitHub can validate the domain and renew
its certificate.

Pushing to `main` redeploys the site, live in about a minute:

```
git add -A && git commit -m "Update portfolio" && git push
```

## Notes

- **Do not delete `CNAME`.** It holds the custom domain; removing it unsets
  `hanees.site` in GitHub Pages.
- `index.html` is a generated bundle (~3.3 MB). Edit it at the source that
  produced it and re-export, rather than hand-editing the bundled file.
- Video embeds load from Vimeo at runtime and need an internet connection.
- The page requests `.image-slots.state.json` and gets a 404. It's a harmless
  leftover probe from the bundler; all images are embedded in the file.
