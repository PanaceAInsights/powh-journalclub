# POWH Dermatology Journal Club

Static site for the Prince of Wales Hospital (POWH) Department of Dermatology journal club.
One folder per monthly edition, each generated from PubMed/NCBI (MEDLINE).

**Live:** <https://panaceainsights.github.io/powh-journalclub/>

## Editions

| | Edition | Theme | Papers | Scope |
|---|---|---|---|---|
| 08 | [August 2026](aug26/) | CME, reviews & guidelines | 40 | JAAD 92(6), 93(1) · AJD 66(4), 66(5) · BJD 192(4)–192(6) |
| 07 | [July 2026](jul26/) | CME, reviews & original research | 58 | JAAD 92(4), 92(5) · AJD 66(3) · BJD 192(3), 192(S1), 192(4) |

## Layout

```
index.html                      landing page — edition tabs
aug26/
  index.html                    screening dashboard
  readinglist.html              printable reading list
  journalclub_aug2026.csv       dataset (23 columns, one row per paper)
jul26/
  index.html                    screening dashboard
  readinglist.html              printable reading list
  journalclubderm2025.csv       dataset
```

Every page carries the same top navigation, so you can move between editions and between
dashboard / reading list / CSV without going back to the landing page.

## The dashboard

- **Filter** by journal, evidence type, topic, issue, article length and your own marks
- **Search** across titles, authors, abstracts and MeSH terms
- **Screen** each paper as Include / Maybe / Exclude, star one as presenting, add notes
- **Keyboard triage** — `j` `k` to move, `i` `m` `x` to mark, `p` to flag as presenting, `?` for the full list
- **Export** the shortlist as Markdown or all decisions as CSV

Screening decisions are held in the browser's `localStorage`. They are private to that browser
and are not uploaded anywhere — export them if you want them to survive a cache clear or move
to another machine.

## How an edition is built

1. Every article indexed in PubMed/MEDLINE for the target issues is retrieved through the NCBI
   E-utilities API (`esearch` scoped by journal + volume + issue, then `efetch`).
2. Records are filtered to that month's scope and classified by evidence type using PubMed
   publication types plus the article title.
3. Section headings — *Continuing Medical Education*, *Clinical Reviews*, *Review Article*,
   *Evidence-Based Dermatology* — are read from each publisher's own table of contents, because
   PubMed does not carry them.
4. Topic tags are derived from MeSH major topics and author keywords.

## Publishing

GitHub Pages serves `main` from the repository root (**Settings → Pages**). Pushing to `main`
redeploys within about a minute. Adding a new edition means dropping in a `mmmyy/` folder and
adding a tab to the landing page and to each page's nav.

---

Bibliographic data and abstracts are © the respective publishers and indexed by the U.S. National
Library of Medicine (PubMed/NCBI). Every entry links to its DOI and PubMed record — always cite
the primary source.
