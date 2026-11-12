# wuwa-vi-chunks

Pre-translated Vietnamese chunk database for **Wuthering Waves**,
used by the [OpenNOW-ORC](https://github.com/duyzoz/OpenNOW-ORC)
client's chunk mode: the client looks a dialogue line up in these files
instead of calling an AI model — no tokens, no translate latency.

- **Game:** Wuthering Waves
- **Version:** 3.8 — "Lilies in a Dying Dream" (textmap from
  [Arikatsu/WutheringWaves_Data](https://github.com/Arikatsu/WutheringWaves_Data),
  branch `3.8`)
- **Translated by:** Muse (55 chunks × 4,000 strings, validated per chunk)
- **Coverage:** 213,384 / 216,384 unique strings (98.6%),
  3,042,056 / 3,133,145 words
- **Status:** chunk 043 is partial (1,000 / 4,000 strings) and being
  finished; everything else is complete.

## Layout

- `manifest.json` — game, version, counts, and the file list. The client
  fetches this first and downloads only the chunk files it does not
  already have cached for this version.
- `chunks/vi_chunk_NNN.json` — one file per translation chunk, in the
  same shape as the client's translation cache:
  `{"version": 1, "entries": {"<english line>": "<vietnamese line>", ...}}`

## Use

The OpenNOW-ORC client (Translation settings → Dịch Chunk → Wuthering
Waves) downloads the manifest + chunk files from this repo
(`raw.githubusercontent.com/huyzoz/wuwa-vi-chunks/main/...`), caches them
locally, and looks OCR'd dialogue lines up in them. Lines the database
does not have fall back to the client's configured AI provider.

## Notes

- Game text © Kuro Games; this repo holds a community Vietnamese
  translation of it, not the original game files.
- The database is refreshed for each game patch (new version = new
  manifest + chunk files).
