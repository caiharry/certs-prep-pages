# GCP Cert Prep — Public Pages

Public GitHub Pages site for CGP-style GCP certification study guides.

This repository is a **git submodule** of the private [certs-prep](https://github.com/caiharry/certs-prep) workspace. It contains only sanitized HTML study guides — no coach notes, AGENTS.md, or internal context.

## Publish workflow

From the parent `certs-prep` repo:

```bash
./scripts/sync-pages.sh
cd certs_prep_pages
git add -A && git commit -m "Sync study guides"
git push
```

GitHub Pages deploys automatically on push to `main`.

## Site URL

https://caiharry.github.io/certs-prep-pages/
