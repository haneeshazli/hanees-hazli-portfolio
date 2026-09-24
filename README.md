# Hanees Hazli — Portfolio

Personal portfolio site, live at **https://hanees.site**

A static site with no build step: `index.html` holds the page markup, styles
and logic, and everything it loads lives in `assets/`:

```
assets/js/     runtime, design system, React, GSAP, ScrollTrigger, Lenis
assets/fonts/  Inter Tight (woff2, split by unicode range)
assets/img/    portrait, tool logos, site screenshots, AI examples (WebP)
```

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
- **Do not delete `.nojekyll`.** It tells GitHub Pages to serve the files
  as-is instead of running them through Jekyll.
- The page used to ship as a single 3.3 MB self-unpacking bundle. It is now
  unpacked into `index.html` + `assets/`, so browsers can cache and
  lazy-load each file. If you re-export from the design tool, unpack the
  export the same way rather than committing the bundle over the top.
- Images are sized for how they're displayed (2–3x for retina). When adding
  one, export WebP at roughly that size rather than the full-resolution
  original.
- Video embeds load from Vimeo at runtime (lazily, as they near the
  viewport) and need an internet connection.
