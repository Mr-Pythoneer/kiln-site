# kiln-site

Public marketing site for **Kiln** — served via GitHub Pages.

This repository is intentionally **public** and contains **only** the landing page.
It holds no source code, no docs, and nothing about how Kiln is built. The Kiln
codebase itself lives in a **separate private repository**.

## Publishing (GitHub Pages)

1. Create a **public** repo named `kiln-site` and push this folder to it.
2. In the repo: **Settings → Pages → Build and deployment**
   - **Source:** *Deploy from a branch*
   - **Branch:** `main` / `/ (root)`
3. The site goes live at `https://<user>.github.io/kiln-site/` within a minute or two.

`.nojekyll` is included so GitHub serves the files as-is (no Jekyll processing).

### Optional: custom domain
Add a `CNAME` file containing your domain and configure DNS per GitHub's docs.

## Before you publish
- Replace the `mailto:hello@example.com` placeholder in `index.html` (search `EDIT ME`)
  with your real contact address or a form link. **Do not** commit a personal email
  you don't want scraped publicly.

## License
© 2026 Kiln. All rights reserved. This content is not licensed for reuse.
