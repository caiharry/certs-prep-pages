# GCP Cert Prep — Public Pages

Public GitHub Pages site for CGP-style GCP certification study guides.

This repository is a **git submodule** of the private [certs-prep](https://github.com/caiharry/certs-prep) workspace. It is the **canonical home for all published HTML** — coach notes, AGENTS.md, and markdown sources stay in the parent repo.

## Edit & publish

```bash
# Edit HTML study guides here in certs_prep_pages/
cd certs_prep_pages
git add -A && git commit -m "Update study guides"
git push
```

GitHub Pages deploys automatically on push to `main`.

Then update the submodule pointer in the parent repo:

```bash
cd ..
git add certs_prep_pages && git commit -m "Update certs_prep_pages submodule pointer"
```

## Site URL

https://caiharry.github.io/certs-prep-pages/
