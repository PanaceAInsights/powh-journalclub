# POWH Dermatology Journal Club

Static site for the Prince of Wales Hospital (POWH) Department of Dermatology journal club.
One folder per monthly edition, each generated from PubMed/NCBI (MEDLINE).

**Live:** <https://panaceainsights.github.io/powh-journalclub/>

## Editions

| | Edition | Theme | Papers | Scope |
|---|---|---|---|---|
| ★ | [BJD Special](bjd-special/) | Review articles & guidelines, with full papers | 10 | BJD 192(5), 192(6), 194(5), 194(6) |
| 11 | [November 2026](nov26/) | CME, reviews & guidelines | 49 (25 new) | JAAD 93(5), 93(6), 94(1) · AJD 66(7), 66(8) · BJD 193(5), 193(6), 194(1) |
| 10 | [October 2026](oct26/) | CME, reviews & guidelines | 38 | JAAD 93(4), 93(5) · AJD 66(7), 66(8) · BJD 193(4), 193(5) |
| 09 | [September 2026](sep26/) | CME, reviews & guidelines | 45 | JAAD 93(2), 93(3) · AJD 66(5), 66(6) · BJD 193(2), 193(3) |
| 08 | [August 2026](aug26/) | CME, reviews & guidelines | 40 | JAAD 92(6), 93(1) · AJD 66(4), 66(5) · BJD 192(4)–192(6) |
| 07 | [July 2026](jul26/) | CME, reviews & original research | 58 | JAAD 92(4), 92(5) · AJD 66(3) · BJD 192(3), 192(S1), 192(4) |

## Layout

```
index.html                      landing page, edition tabs
bjd-special/
  index.html                    special edition: BJD reviews & guidelines with full papers
  journalclub_bjd_special.csv   dataset (27 columns, one row per paper)
  papers/                       open-licence PDFs only (CC BY, CC BY-NC); the rest link to OUP
nov26/
  index.html                    screening dashboard (adds running-order planner, October carry-over)
  readinglist.html              printable reading list
  journalclub_nov2026.csv       dataset (23 columns, one row per paper; adds Seen_In)
oct26/
  index.html                    screening dashboard (adds triage mode, evidence map, import)
  readinglist.html              printable reading list
  journalclub_oct2026.csv       dataset (22 columns, one row per paper)
sep26/
  index.html                    screening dashboard
  readinglist.html              printable reading list
  journalclub_sep2026.csv       dataset (22 columns, one row per paper)
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
- **Keyboard triage**: `j` `k` to move, `i` `m` `x` to mark, `p` to flag as presenting, `?` for the full list
- **Export** the shortlist as Markdown or all decisions as CSV
- **Triage mode** (October onward): `t` opens one paper at a time, full abstract, decide and move on
- **Evidence map** (October onward): journal × evidence-type grid that doubles as a filter
- **Import** a decisions CSV back in, to move marks between machines or merge a colleague's
- **Running order** (November onward): `r` opens a planner for the shortlist: drag into order, name presenters,
  set minutes and a start time, see any overrun, then copy or print the agenda
- **Repeat papers** (November onward): papers already listed in the previous edition are tagged, can be filtered
  out, and their earlier screening marks can be brought across in one click

Screening decisions are held in the browser's `localStorage`. They are private to that browser
and are not uploaded anywhere. Export them if you want them to survive a cache clear or move
to another machine.

## How an edition is built

1. Every article indexed in PubMed/MEDLINE for the target issues is retrieved through the NCBI
   E-utilities API (`esearch` scoped by journal + volume + issue, then `efetch`).
2. Records are filtered to that month's scope and classified by evidence type using PubMed
   publication types plus the article title.
3. Section headings such as *Continuing Medical Education*, *Clinical Reviews*, *Review Article*
   and *Evidence-Based Dermatology* are read from each publisher's own table of contents, because
   PubMed does not carry them.
4. Topic tags are derived from MeSH major topics and author keywords.

## Publishing

GitHub Pages serves `main` from the repository root (**Settings → Pages**). Pushing to `main`
redeploys within about a minute. Adding a new edition means dropping in a `mmmyy/` folder and
adding a tab to the landing page and to each page's nav.

---

Bibliographic data and abstracts are © the respective publishers and indexed by the U.S. National
Library of Medicine (PubMed/NCBI). Every entry links to its DOI and PubMed record, so always cite
the primary source.
