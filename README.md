<p align="center">
  <img src="assets/header.svg" alt="header" width="100%">
</p>

<p align="center">
  <a href="https://huggingface.co/datasets/theelderemo/genius-lyrics-cleaned">
    <img src="assets/hfbadges.svg" alt="hfbadge">
  </a>
</p>

<p align="center">
  <img src="assets/doibadge.svg" alt="DOI">
</p>

A heavily cleaned, English-only, genre-filtered subset of the [Genius Song Lyrics with Language Information](https://www.kaggle.com/datasets/carlosgdcj/genius-song-lyrics-with-language-information) Kaggle dataset. Reduced from **9+ GB to 2.56 GB** through language filtering, genre filtering, artifact removal, and deduplication. Optimized for language model fine-tuning, lyric generation, and music NLP research.  

<p align="center">
  <img src="assets/singledivider.svg" alt="divider">
</p>

<p align="center">
  <img src="assets/heading-nosplits.svg" alt="No train/validation/test splits" width="100%">
</p>

This dataset ships as a single `train` split. You should create validation and test splits appropriate to downstream task  

<p align="center">
  <img src="assets/heading-overview.svg" alt="Overview" width="100%">
</p>  

<br>

The raw Genius dataset contains millions of song entries across dozens of languages, genres, and quality levels — including non-music content like poetry, book excerpts, and miscellaneous text tagged as `misc`. This cleaned version retains only **English-language songs from verified music genres**, with lyrics scrubbed of Genius UI artifacts, HTML residue, and duplicates. The result is a high-signal corpus suitable for causal language model pretraining or supervised fine-tuning on lyric generation tasks.

<p align="center">
  <img src="assets/heading-datasetstats.svg" alt="Dataset Stats" width="100%">
</p>

<p align="center">
  <img src="assets/table-datasetstats.svg" alt="Dataset Stats Table" width="100%">
</p>

<p align="center">
  <img src="assets/heading-cleaningpipeline.svg" alt="Cleaning Pipeline" width="100%">
</p>  

<br>

**The following steps were applied in order:**

</div>

1. **Language filter** — Retained only rows where `language == 'en'`, removing all non-English entries.
2. **Genre filter** — Dropped the `misc` tag (which contains books, poems, speeches, and other non-music content). Retained only the 15 confirmed music genre tags listed below.
3. **Artifact removal** — Applied regex cleaning to remove:
    - Genius embed counters (e.g., `1234Embed` at end of lyrics)
   - UI strings like `"See [Artist] Live"`, `"Get tickets"`, `"You might also like"`
   - Residual HTML tags (`<...>`)
4. **Section header normalization** — Simplified attributed headers: `[Chorus: Cam'ron & Jay-Z]` → `[Chorus]`, preserving verse structure while removing contributor meta.
5. **Whitespace normalization** — Collapsed 3+ consecutive newlines to 2, and collapsed horizontal whitespace.
6. **Stub removal** — Dropped any entry whose cleaned lyrics are under 100 characters.
7. **Exact deduplication** — Removed entries with identical cleaned lyrics.
8. **Near-deduplication** — For entries sharing the same `artist` + `title`, retained the version with the highest view count.

<p align="center">
  <img src="assets/heading-datastructure.svg" alt="Data Structure" width="100%">
</p>

<p align="center">
  <img src="assets/table-datastructure.svg" alt="Data Structure Table" width="100%">
</p>

<p align="center">
  <img src="assets/genre-values.svg" alt="Genre Values" width="100%">
</p>

<p align="center">
  <img src="assets/heading-trainingformat.svg" alt="Training Format" width="100%">
</p>

<p align="center">
  <img src="assets/text-trainingformat.svg" alt="Training Format Description" width="100%">
</p>

<p align="center">
  <img src="assets/codeblock-trainingformat.svg" alt="Training Format Code" width="100%">
</p>

<p align="center">
  <img src="assets/text-softconditioning.svg" alt="Soft Conditioning" width="100%">
</p>

<p align="center">
  <img src="assets/heading-tokenlength.svg" alt="Token Length Distribution" width="100%">
</p>

<p align="center">
  <img src="assets/text-tokenlength.svg" alt="Token Length Details" width="100%">
</p>

<p align="center">
  <img src="assets/heading-sources.svg" alt="Sources" width="100%">
</p>

<p align="center">
  <img src="assets/blockquote-sources.svg" alt="Sources List" width="100%">
</p>

<p align="center">
  <img src="assets/text-sources.svg" alt="Sources Note" width="100%">
</p>

<p align="center">
  <img src="assets/heading-curation.svg" alt="Curation" width="100%">
</p>

<p align="center">
  <img src="assets/text-curation.svg" alt="Curation Details" width="100%">
</p>

<p align="center">
  <img src="assets/heading-citation.svg" alt="Citation" width="100%">
</p>

If you use this dataset in research or a project, please cite both the upstream Kaggle source and this repository:

```bibtex
@misc{christopher_dickinson_2026,
	author       = { Christopher Dickinson },
	title        = { genius-lyrics-cleaned (Revision 9742989) },
	year         = 2026,
	url          = { https://huggingface.co/datasets/theelderemo/genius-lyrics-cleaned },
	doi          = { 10.57967/hf/7978 },
	publisher    = { Hugging Face }
}
```