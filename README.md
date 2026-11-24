# The Rhemes New Testament (1582) — TEI XML Edition

A complete, print-verified, open TEI P5 XML edition of the **1582 Rhemes New Testament** (*The Nevv Testament of Iesvs Christ, translated faithfully into English out of the authentical Latin…*, Rhemes: John Fogny, 1582; STC 2884).

This edition starts from the [EEBO-TCP](https://textcreationpartnership.org/) transcription (`A16049`) and systematically restores what the original keying left out or misread, checking the full 800-page volume against high-resolution 1582 facsimiles. The goal is faithful diplomatic transcription — preserving original 1582 spelling, long-s (`ſ`), `vv`, macrons, marginal notes, annotations, and original-language citations.

## Contents

| File | Description |
| :--- | :--- |
| [`A16049.xml`](A16049.xml) | The complete TEI P5 XML edition (all 800 pages). |
| [`RULES.md`](RULES.md) | Editorial and transcription conventions. Read before editing. |

## What's Improved Over the Original EEBO-TCP Release

The raw EEBO-TCP Phase I file contained **2,411 missing-text `<gap>` placeholders** (all Greek, Hebrew, and Aramaic omitted, plus thousands of illegible smudges), **50 accidental microfilm retakes**, and hundreds of typist errors. Every gap has now been restored and verified against the 1582 print:

| Metric | Original EEBO-TCP | This Edition |
| :--- | ---: | ---: |
| Unresolved `<gap>` placeholders | 2,411 | **0** *(100% restored)* |
| Foreign-script citations (`<foreign>`) | 0 | **327** *(319 Greek, 7 Hebrew, 1 Aramaic)* |
| Small-caps markup (`<hi rend="smallcaps">`) | 0 | **863** |
| Page breaks (`<pb>`) | 852 | **802** *(50 microfilm duplicates removed)* |
| Unicode normalization | Mixed | **Strict NFC** |

### Highlights
- **Zero remaining gaps**: Every illegible word, citation, marginal note, and non-Latin script passage across all 800 pages (front matter, Gospels, Acts, Epistles, Apocalypse, and back-matter tables/errata) has been restored from the 1582 facsimiles.
- **Original Greek, Hebrew & Aramaic restored**: All 327 foreign-language passages are encoded in Unicode with accents, breathings, and language tags (`xml:lang="grc"`, `"he"`, `"arc"`).
- **Typist errors & milestones fixed**: Over a thousand EEBO-TCP misreads, dropped words, duplicate lines, and missing verse/page milestones have been corrected without modernizing genuine 1582 spellings or print misprints.
- **Clean reading flow**: The 50 accidental EEBO reel-2646 microfilm duplicate frames were removed from the text and preserved in a `<back>` appendix register (`<div type="appendix" subtype="microfilm_duplicates">`).

## Encoding at a Glance

- **Standard:** TEI P5, strict Unicode NFC, validated well-formed XML.
- **1582 typography:** Preserves long-s (`ſ`), `vv`, `u`/`v`, ligatures (`æ`, `œ`), macron suspensions (`<g ref="char:cmbAbbrStroke">`), and line-end hyphens (`<g ref="char:EOLhyphen"/>`).
- **Display & structure:** Small caps use `<hi rend="smallcaps">`, drop initials use `<seg rend="decorInit">`, marginalia use `<note place="margin">`, and verse/chapter numbers use `<label type="milestone">`.

## Sources

1. High-resolution facsimiles of the 1582 first edition (Sancta Clara, Peters, and Bodleian copies; ProQuest EEBO reel 2646).
2. [English Wikisource critical transcription](https://en.wikisource.org/wiki/Index:1582_Rhemes_New_Testament.pdf) (all 800/800 pages live and kept in sync with this repository).

## License

The EEBO-TCP Phase I text is released under [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/). All corrections and enhancements in this repository are likewise dedicated to the public domain under CC0 1.0.
