# GCP Cert Prep — Public Pages

Public GitHub Pages site for GCP certification study guides.

This repository is a **git submodule** of the private [certs-prep](https://github.com/caiharry/certs-prep) workspace. It is the **canonical home for all published HTML** — coach notes, AGENTS.md, and markdown sources stay in the parent repo.

## Edit & publish

```bash
# Edit HTML study guides here in certs_prep_pages/
cd certs_prep_pages
git add -A && git commit -m "Update study guides"
git push
```

GitHub Pages deploys automatically on push to `main`.

## Visual skins (A/B/C)

The portal ships in **three visual skins** of one design system, for comparison
testing with colleagues. The root [`index.html`](index.html) is a chooser that
routes into a skin (or randomly assigns + remembers one):

| Skin | URL | Feel |
|---|---|---|
| Academy | [`academy/`](academy/) | Ovo + Work Sans, alchemy blue, soft border-matched block shadows |
| Sticker Book | [`sticker/`](sticker/) | Comic Neue, heavy black blocks — the original CGP feel |
| Briefing | [`briefing/`](briefing/) | Hairline cards, quiet colour, no block shadows |

- **Design tokens & skin sheets** live in [`assets/ds/`](assets/ds/)
  (`tokens.css` is the single source of truth; `skin-*.css` are the three skins).
- **Source of truth = the unskinned pages** in each `<cert>/` folder. The skin
  folders are **generated** — never hand-edit them.
- Edit a guide in `<cert>/`, tweak a look in `assets/ds/skin-*.css`, then
  regenerate from the parent repo:

```bash
cd ..              # parent certs-prep repo
python3 build_skins.py
```

This rewrites `academy/`, `sticker/` and `briefing/` from the `<cert>/` sources.


Then update the submodule pointer in the parent repo:

```bash
cd ..
git add certs_prep_pages && git commit -m "Update certs_prep_pages submodule pointer"
```

## Site URL

https://caiharry.github.io/certs-prep-pages/
