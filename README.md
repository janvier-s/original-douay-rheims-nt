# The Rhemes New Testament (1582) — TEI XML Edition

A corrected, open TEI P5 XML edition of the **1582 Rhemes New Testament** ("The Nevv Testament of Iesvs Christ, translated faithfully into English out of the authentical Latin…", Rhemes: John Fogny, 1582; STC 2884).

The base text is the [EEBO-TCP](https://textcreationpartnership.org/) transcription `A16049`. That transcription has many gaps and typist errors, so this repository audits it page by page against the 1582 print and corrects it. The goal is to reproduce the print faithfully, including its spelling, long-s, marginal notes, annotations and Greek.

## Contents

| File | Description |
| :--- | :--- |
| [`A16049.xml`](A16049.xml) | The edition (TEI P5). |
| [`RULES.md`](RULES.md) | Editorial and transcription conventions. Read before editing. |

## Audit status

| Section | Status |
| :--- | :--- |
| Front matter (Censure, Preface, Signification of Numbers, Books of the NT) | Done |
| Matthew, Mark, Luke, John | Done (gaps restored, small caps tagged, Unicode NFC) |
| Acts of the Apostles and end-matter | Audited for transcription errors |
| General Argument of the Epistles, Romans | In progress (through Rom. 1:27) |
| Remaining Epistles, Apocalypse | Audited during Wikisource production |
| Back matter (Tables of Epistles & Gospels, Controversies, Hard Words, Errata) | Done (41 gaps incl. 4 Greek readings restored, 44 typist errors fixed, NFC) |

Each audited section has had its gaps filled from the print (polytonic Greek in `<foreign xml:lang="grc">`), its typist errors corrected, small capitals tagged and its text normalised to NFC.

### Current counts

| Element | Count |
| :--- | ---: |
| `<gap>` (still unresolved) | 1,521 (1,294 illegible, 227 foreign) |
| `<foreign>` | 98 |
| `<note>` | 5,955 |
| `<pb>` | 802 |

Re-count these whenever gaps are filled (see [RULES.md §9](RULES.md)).

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
