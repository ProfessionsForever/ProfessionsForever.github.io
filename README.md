# ProfessionsForever website

The website for the [ProfessionsForever](https://github.com/ProfessionsForever/Professions_Forever) addon for WoW: Forever. It is plain HTML and CSS, with no build step and no dependencies.

| File | Purpose |
| --- | --- |
| `index.html` | The homepage: features, integrations, install steps, slash commands, FAQ |
| `changelog.html` | Release notes, **generated**: don't edit by hand |
| `assets/` | Stylesheet, icon and favicon |
| `assets/screenshots/` | The banner and in-game screenshots used on the homepage; click any to open it full size |
| `tools/gen_site.py` | Rebuilds `changelog.html` from the addon's `CHANGELOG.md` |
| `.nojekyll` | Tells GitHub Pages to serve the files as they are |
| `sitemap.xml` | Lists the pages for search engines; submit it in Google Search Console |

## Updating the changelog

The changelog lives only in the addon repository. After a release is pushed, run:

```sh
python3 tools/gen_site.py
```

It downloads `CHANGELOG.md` from the addon repository's `main` branch and rebuilds `changelog.html`. To build from a local changelog that isn't pushed yet, pass its path:

```sh
python3 tools/gen_site.py ../Professions_Forever/CHANGELOG.md
```

When a release changes the headline features or the version, update `index.html` by hand: the version under the buttons, the "New in" section, and the feature cards.

## Previewing

Open `index.html` in a browser, or run `python3 -m http.server` here and visit http://localhost:8000.

## Publishing with GitHub Pages

In the repository's **Settings, Pages**, choose **Deploy from a branch**, the `main` branch and the `/ (root)` folder.

The site is published at https://professionsforever.github.io/. If it ever moves, update the canonical and `og:` links in `index.html`, the canonical link in `tools/gen_site.py`, and `sitemap.xml`.
