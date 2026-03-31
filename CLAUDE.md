# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **data-only repository** containing the latest 2025 HSK (Hanyu Shuiping Kaoshi / Chinese proficiency test) vocabulary, characters, and grammar data pulled directly from official sources. There are no build tools, scripts, tests, or dependencies — just structured data files.

The 2025 data has changed from the original 2021 HSK 3.0 release. This repo is used to explore the current data and compare against previous versions.

## Data Files

### TSV datasets (HSK 3.0, sourced from chinesetest.cn)

| File | Records | Columns |
|------|---------|---------|
| `vocabulary.tsv` | ~11,000 | `type`, `word`, `pinyin`, `cixing` (part of speech), `sort`, `levelName` (一级–七-九级) |
| `grammar.tsv` | ~593 | `examLevelId` (HSK1–HSK9), `content`, `grammarType`, `categoryType`, `grammarDetail`, `cases` |
| `hanzi.tsv` | ~4,288 | `examLevelId` (HSK1–HSK9), `word`, `type` |

- `vocabulary.tsv` uses Chinese level names (一级 = Level 1, 七-九级 = Levels 7-9)
- `grammar.tsv` and `hanzi.tsv` use English-style level IDs (HSK1, HSK2, etc.)
- In `grammar.tsv`, multi-line `cases` examples are joined with `|`

## Comparison Data Sources

For comparing against previous HSK versions, word lists from the MteH corpus are available at:
- https://github.com/becky82/mteh/tree/master/sources — contains HSK 2.0, HSK 3.0, and other Chinese character/word sources. Note: MteH calls the 2025 HSK data "HSK 3.1".

## Key Gotchas

- HSK 3.0 has separate word and character lists (unlike HSK 2.0 where characters are derived from words).
- Level numbering differs between files: Chinese numerals in `vocabulary.tsv` vs "HSK1" format in the other TSV files.
