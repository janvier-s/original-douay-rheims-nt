# The Rhemes New Testament (1582) — TEI XML Edition

A corrected, open TEI P5 XML edition of the **1582 Rhemes New Testament** ("The Nevv Testament of Iesvs Christ, translated faithfully into English out of the authentical Latin…", Rhemes: John Fogny, 1582; STC 2884).

The base text is the [EEBO-TCP](https://textcreationpartnership.org/) transcription `A16049`. That transcription has many gaps and typist errors, so this repository audits it page by page against the 1582 print and corrects it. The goal is to reproduce the print faithfully, including its spelling, long-s, marginal notes, annotations and Greek.

## Contents

| File | Description |
| :--- | :--- |
| [`A16049.xml`](A16049.xml) | The edition (TEI P5). |
| [`RULES.md`](RULES.md) | Editorial and transcription conventions. Read before editing. |

## Improvements over the original EEBO-TCP file

Compared with the raw EEBO-TCP Phase I release (`ee79a5e`), `A16049.xml` has undergone **40+ audit commits** (`1,784` insertions, `3,532` deletions) against high-resolution 1582 facsimiles (Sancta Clara, Peters, and Bodleian copies):

| Element / Metric | Original EEBO-TCP | Current Edition | Change |
| :--- | ---: | ---: | :--- |
| `<gap>` (total) | 2,411 | 1,521 | **−890 (−36.9%)** |
| — `<gap reason="illegible">` | 2,034 | 1,294 | **−740 restored** |
| — `<gap reason="foreign">` (Greek, etc.) | 327 | 227 | **−100 restored** |
| — `<gap reason="duplicate">` (microfilm retakes) | 50 | 0 | **−50 removed** (documented in `<back>` register) |
| `<foreign xml:lang="grc">` (polytonic Greek) | 0 | 98 | **+98 restored** with accents &amp; breathings |
| `<hi rend="smallcaps">` | 0 | 859 | **+859 tagged** (sacred names, headings, post-drop-cap) |
| `<pb>` page milestones | 852 | 802 | **−50 duplicate microfilm exposures removed** |
| `<note>` marginalia | 5,954 | 5,955 | **+1 restored** (and duplicates deduplicated) |

### Key editorial improvements by section

- **Front matter (pp. 1–30)**: Complete facsimile audit (60+ typist errors corrected, gaps filled, small caps and Unicode NFC normalized across the Censure, Preface to the Reader, Signification of Numbers &amp; Marks, and Books of the NT).
- **Four Gospels (Matthew–John, pp. 31–308)**: Full gap restoration, polytonic Greek restoration in `<foreign xml:lang="grc">`, small-cap tagging of sacred names and display text, and hundreds of typist/contraction errors corrected against the 1582 print.
- **Evangelical History &amp; Acts End-Matter Tables (pp. 309–313, 402–404)**: Chapter references, narrative text, Latin citations, and Apostles' Creed audited and restored against the facsimiles.
- **Acts of the Apostles (pp. 314–401)**: 58+ EEBO-TCP transcription errors corrected and normalized to Unicode NFC.
- **Epistles &amp; Apocalypse (pp. 405–773)**: General Argument &amp; Romans 1:1–27 fully audited; targeted gap, Greek, milestone-anchor, and typist fixes applied across Philemon, Hebrews, James, 1–2 Peter, 1–3 John, Jude, and Apocalypse during full 800-page Wikisource production.
- **Back matter (pp. 774–800)**: Complete audit of the Table of Epistles &amp; Gospels, Table of Controversies, Explication of Hard Words, and Errata (*The faultes correcte thus.*) — all **41 gaps** restored (including 4 Greek readings: `μετάνοια`, `μετανοεῖν`, `ἃ ἐυλογοῦμεν`, `ὃ ἐυλογοῦμεν`) and **44 typist errors** corrected.
- **Structural &amp; encoding hygiene**: All 50 accidental EEBO reel-2646 duplicate microfilm frames removed from inline reading flow and preserved in a `<back>` appendix register; full text normalized to strict Unicode NFC; XML validated well-formed on every commit.

## Audit status

| Section | Status |
| :--- | :--- |
| Front matter (Censure, Preface, Signification of Numbers, Books of the NT) | Done |
| Matthew, Mark, Luke, John | Done (gaps restored, small caps tagged, Unicode NFC) |
| Evangelical History &amp; Acts end-matter tables (pp. 309–313, 402–404) | Done |
| Acts of the Apostles | Audited for transcription errors |
| General Argument of the Epistles, Romans | In progress (through Rom. 1:27) |
| Remaining Epistles, Apocalypse | Targeted gaps, Greek, milestones &amp; typos fixed during Wikisource production |
| Back matter (Tables of Epistles &amp; Gospels, Controversies, Hard Words, Errata) | Done (41 gaps incl. 4 Greek readings restored, 44 typist errors fixed, NFC) |

Each audited section has had its gaps filled from the print (polytonic Greek in `<foreign xml:lang="grc">`), its typist errors corrected, small capitals tagged and its text normalised to NFC.

Re-count the XML elements whenever gaps are filled (see [RULES.md §9](RULES.md)).

## Encoding

- **Standard:** TEI P5.
- **Early modern typography:** long-s (`ſ`), ligatures and abbreviations are preserved. Macron suspensions use `<g ref="char:cmbAbbrStroke">`, and line-end hyphens use `<g ref="char:EOLhyphen"/>`.
- **Small capitals:** `<hi rend="smallcaps">`. Drop initials use `<seg rend="decorInit">`.
- **Foreign text:** `<foreign xml:lang="grc">` for Greek and similar elements for other languages.
- **Marginalia:** `<note place="margin">`.
- **Verse and chapter labels:** `<label type="milestone">`.
- **Unresolved text:** `<gap reason="illegible|foreign"/>`.

### Microfilm duplicate exposures

EEBO reel 2646 contains 50 accidental duplicate frames (re-takes of pages already transcribed). They are removed from the body text and listed in a register in `<back>` (`<div type="appendix" subtype="microfilm_duplicates">`). No text is missing because of them.

## Sources

1. The 1582 print: ProQuest EEBO microfilm, reel 2646.
2. The Peters facsimile edition and other facsimiles of the 1582 print.
3. [Critical transcription on English Wikisource](https://en.wikisource.org/wiki/Index:The_New_Testament_of_Iesus_Christ_(1582).djvu), which is kept in step with this edition.

## License

The EEBO-TCP Phase I text is released under [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/). The corrections in this repository are likewise dedicated to the public domain under CC0 1.0.
