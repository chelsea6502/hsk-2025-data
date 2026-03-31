# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **data-only repository** containing the latest 2025 HSK (Hanyu Shuiping Kaoshi / Chinese proficiency test) vocabulary, characters, and grammar data pulled directly from official sources. There are no build tools, scripts, tests, or dependencies — just structured data files.

The 2025 data has changed from the original 2021 HSK 3.0 release. This repo is used to explore the current data and compare against previous versions.

Two HSK standards are represented:
- **HSK 3.0** (current 2025 official data): primary dataset, 7 levels (1–6 plus 7–9), ~11,000 words total
- **HSK 2.0** (legacy): reference dataset, 6 levels, ~5,000 words total

## Data Files

### Main JSON datasets (HSK 3.0, sourced from chinesetest.cn)

| File | Records | Schema |
|------|---------|--------|
| `vocabulary.json` | ~11,000 | `type`, `word`, `pinyin`, `cixing` (part of speech), `sort`, `levelName` (一级–七-九级) |
| `grammar.json` | ~593 | `examLevelId` (HSK1–HSK9), `content`, `grammarType`, `categoryType`, `grammarDetail`, `cases` |
| `hanzi.json` | ~4,288 | `examLevelId` (HSK1–HSK9), `word`, `type` |

- `vocabulary.json` uses Chinese level names (一级 = Level 1, 七-九级 = Levels 7-9)
- `grammar.json` and `hanzi.json` use English-style level IDs (HSK1, HSK2, etc.)

### Comparison text files (`mteh-sources/`)

Previous HSK word lists (from the MteH corpus) used for comparing against the current official data. Plain text, one word per line. See the `readme.md` in each subdirectory for important caveats:
- **Variant forms**: `爸爸|爸` means word has an alternate form
- **Parenthetical usage**: `第（第二）` shows contextual usage
- **Duplicates exist** across levels (e.g., 一下儿 appears in both HSK1 and HSK5)
- **Grammar structures** mixed in with vocabulary in HSK 2.0 (e.g., `虽然……但是……`)

## Key Gotchas

- The `mteh-sources/` directory is **untracked** — it contains previous HSK word lists from the MteH corpus, used for comparison against the current 2025 data.
- HSK 3.0 has separate word and character lists (unlike HSK 2.0 where characters are derived from words).
- Level numbering differs between files: Chinese numerals in `vocabulary.json` vs "HSK1" format in the other JSON files.
