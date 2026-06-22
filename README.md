# Aldermere — Luxury Home Remodeling Website

**This is a STATIC HTML / CSS / JS website.** (Not React, not Vite — that
experiment was removed and archived in `_archive-react/`.)

## The only 3 folders that matter

| Folder | What it is | Do you touch it? |
|--------|-----------|------------------|
| **project root** (`index.html`, the other `.html` pages, `css/`, `js/`, `public/`) | **Source of truth — EDIT HERE** | ✅ Edit |
| **`deployment-package/`** | The finished site to publish (CSS inlined, self-contained) | ⬆️ Upload this |
| everything else (`hosting-export/`, `legacy-html/`, `_archive-react/`, `node_modules/`) | build leftovers / backups | ❌ Ignore (safe to delete) |

## Run it locally
```bash
npm start
```
Opens at **http://localhost:4321** — that's the source site you edit.

## Publish it (Option B — static hosting)
```bash
npm run build          # refreshes deployment-package/ from the root source
```
Then **upload the *contents* of `deployment-package/`** to your host so that
`index.html` sits at the site root (with `images/`, `videos/`, `.nojekyll`
beside it).

- **Netlify / Vercel / Cloudflare Pages:** drag in the contents of
  `deployment-package/`. No build command on their side — it's already built.
- **GitHub Pages:** put the contents at the repo root (keep `.nojekyll`),
  then Settings → Pages → Deploy from a branch → `main` → `/ (root)`.
- **cPanel / FTP:** upload the contents into `public_html/`.

Why `deployment-package/` and not the raw root? Its CSS is inlined into every
page, so the styling can never fail to load (that was the cause of the earlier
"blank/unstyled" uploads).

## Editing tips
- Pages, styling, videos, images all live in the root: `*.html`, `css/`,
  `js/`, `public/`.
- After any edit, run `npm run build` again before uploading.
