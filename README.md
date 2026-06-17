# Dermatology Journal Club

Static site (auto-generated from PubMed/NCBI). The home page is the interactive
article dashboard for the Prince of Wales Hospital (POWH) Department of
Dermatology journal club.

## Files
- **`index.html`** — interactive dashboard (search + filter by journal/type, per-paper cards with abstracts). This is the home page.
- **`reading-list.html`** — printable reading list, every abstract inline (good for a PDF handout).
- **`journal-club-derm-2025.csv`** — one row per paper incl. abstract (opens in Excel; imports into EndNote/Zotero).

## Publish it on GitHub Pages
1. Create a new repository (e.g. `derm-journal-club`) and upload these files to it.
2. In the new repo: **Settings → Pages → Build and deployment → Source: "Deploy from a branch" → Branch: `main` / `(root)` → Save.**
3. Wait ~1 minute. The site goes live at:
   `https://<your-username>.github.io/<repo-name>/`
   (the dashboard, because it's `index.html`).

If the repo is **private**, free GitHub Pages won't serve it — make the repo public, or deploy with Vercel ([vercel.com/new](https://vercel.com/new) → import the repo → Deploy).

## Scope (58 papers)
- **JAAD** Vol 92, Iss 4–5 (Apr–May 2025): CME/review + original
- **AJD** Vol 66, Iss 3 (May 2025): full issue
- **BJD** Vol 192 reviews (Feb–Mar 2025) + adjacent

Bibliographic data © the respective publishers, indexed by the U.S. National
Library of Medicine (PubMed/NCBI). Every entry links to its DOI and PubMed
record — always cite the primary source.
