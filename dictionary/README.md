# Kotoba dictionary sources and updates

Japanese–English dictionary data: **JMdict**, copyright James William BREEN and the Electronic Dictionary Research and Development Group (EDRDG). Used under **Creative Commons Attribution–ShareAlike 4.0**.

- [JMdict documentation](https://www.edrdg.org/wiki/Main_Page.html)
- [EDRDG dictionary licence and copyright notice](https://www.edrdg.org/edrdg/licence.html)
- [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)
- [Download this dictionary derivative](jmdict.json.gz)
- [Snapshot metadata and source checksum](metadata.json)

Changes: English-gloss entries converted from XML to compact JSON; readings, spelling notes, part of speech, usage labels, sense restrictions, and common-word priorities retained. Dictionary derivatives in this directory are shared under CC BY-SA 4.0. This licence does not change the separate rights in application code, course content, or Culture quotations.

The 1,500 course and Culture examples are an independently labeled search index of this website’s learning materials, not JMdict example sentences. Culture excerpt attributions remain on their linked pages.

## Refresh procedure

Before publication, and at least monthly for an ongoing hosted dictionary service, download a current `JMdict_e.gz` from the publisher. Preserve HTTPS certificate verification. From the project directory run:

```sh
python3 outputs/kotoba/course-authoring/dictionary/build_dictionary.py work/dictionary/JMdict_e.gz
node outputs/kotoba/course-authoring/dictionary/lookup.test.cjs
```

The builder refreshes both dictionary formats, source metadata, and the course/Culture example index. Review the resulting counts and run browser checks before distributing an update. The current files are a local review snapshot, not a live feed.

## Search behavior and privacy

A Web Worker loads the dictionary on first opening (about 9 MB compressed; an uncompressed fallback is provided). Japanese and English lookup, Unicode width normalization, katakana/hiragana equivalence, common-word ranking, and partial matches run locally. Search text is not sent to a dictionary API, analytics service, or translator. No query history is saved by the feature. Ordinary browser caching may retain the dictionary data; the feature does not guarantee offline availability.

This is a word and expression dictionary, not a whole-sentence translation model. Verb inflections are not automatically deconjugated; use the dictionary form when a lookup does not match. Romanized Japanese is not automatically converted to kana. Meanings vary by context, and matching a reading does not certify pitch accent. Example playback uses the site’s existing labeled synthesized standard Japanese audio.
