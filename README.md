# web_portal — the files that go on the internet

Everything in this folder is what gets copied to GitHub. Nothing else from `the_banker` should be published
(no `filings/`, no CSVs, no `holdings.md` / `profile.md` / `analysis/`).

## Contents
| File | What it is |
|---|---|
| `index.html` | The dashboard. One self-contained file: data, styles, script and the GinerFX logo are all embedded. **Generated** by `dashboard/build.py`, which writes it straight here (this is the only copy; there is none in `dashboard/`). Do not edit it by hand. |
| `.nojekyll` | Empty file that tells GitHub Pages to serve the files as they are. |
| `README.md` | This note (you can leave it out of the repository). |

The page has four sections (Overview, Positions, Calendar, Framework) inside this one file, chosen by `#overview`, `#positions`, `#calendar`, `#framework` in the address; Overview opens by default; Framework is a placeholder.

Add any future web files here (extra pages, a custom domain `CNAME` file, images, ...).

## Update the page
1. Change data or design in `dashboard/` (see `dashboard/CLAUDE.md`).
2. Run `python build.py` inside `dashboard/`. This rewrites `web_portal/index.html`.
3. Copy the contents of `web_portal/` to your GitHub repository (replace `index.html`), commit, push.

## Publish on GitHub Pages (first time)
1. Create a repository on GitHub (for example `the-banker-dashboard`), public if you want the free Pages plan.
2. Upload `index.html` and `.nojekyll` to the root of the repository (web upload or `git push`).
3. Repository Settings > Pages > Source: "Deploy from a branch", branch `main`, folder `/ (root)`.
4. The page appears at `https://<your-user>.github.io/<repository>/` after a minute or two.

## Before you publish (checks)
- The page is **public to anyone with the link**. It has `noindex, nofollow` (search engines are asked not to list it) but it is not private.
- It contains only public company financials taken from official filings, plus the GinerFX logo. No holdings, weights or personal data. Re-check this before connecting the dashboard to `holdings.md`.
- It shows data as of the last build; the figures are reported statement numbers, not investment advice.
