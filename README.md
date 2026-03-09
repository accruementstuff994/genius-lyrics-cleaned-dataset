# Genius English Song Lyrics – Cleaned & Deduplicated  
- [Hugging Face Dataset](https://huggingface.co/datasets/theelderemo/genius-lyrics-cleaned)

A heavily cleaned, English-only, genre-filtered subset of the [Genius Song Lyrics with Language Information](https://www.kaggle.com/datasets/carlosgdcj/genius-song-lyrics-with-language-information) Kaggle dataset. Reduced from **9+ GB to 2.56 GB** through language filtering, genre filtering, artifact removal, and deduplication. Optimized for language model fine-tuning, lyric generation, and music NLP research.

- **No train/validation/test splits**: This dataset ships as a single `train` split. You should create validation and test splits appropriate to downstream task

|            DOI           | Revision |
|:------------------------:|:--------:|
| 10.57967/hf/7978 Current | 9742989  |

### Overview

The raw Genius dataset contains millions of song entries across dozens of languages, genres, and quality levels — including non-music content like poetry, book excerpts, and miscellaneous text tagged as `misc`. This cleaned version retains only **English-language songs from verified music genres**, with lyrics scrubbed of Genius UI artifacts, HTML residue, and duplicates. The result is a high-signal corpus suitable for causal language model pretraining or supervised fine-tuning on lyric generation tasks.

### Dataset Stats

| Metric | Value |
|---|---|
| Total rows | 3,179,588 |
| Dataset size | ~4.51 GB |
| Download size | ~2.38 GB |
| Split | train only |
| Path | data/train-* |
| num_bytes | 4847179321 |
| num_examples | 3179588 |
| task_categories | text-generation |
| task_ids | language-modeling |
| size_categories | 1M<n<10M |

### Cleaning Pipeline

The following steps were applied in order:

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

### Dataset Structure

| Field    | Type    | Description                                                                 |
|----------|---------|-----------------------------------------------------------------------------|
| `title`  | string  | Song title as listed on Genius                                              |
| `artist` | string  | Primary artist name                                                         |
| `tag`    | string  | Genre tag (one of 15 values; see below)                                     |
| `year`   | float64 | Release year (may be `NaN` for entries with missing metadata)              |
| `lyrics` | string  | Cleaned, deduplicated song lyrics with normalized section headers           |

The dataset includes the following 15 genre values:

`rap` · `trap` · `pop` · `rb` · `rock` · `country` · `metal` · `folk` · `jazz` · `indie` · `electronic` · `reggae` · `soul` · `blues` · `latin`

### Training Format

Each row's `lyrics` field contains plain cleaned lyrics with normalized section headers (`[Verse 1]`, `[Chorus]`, `[Bridge]`, etc.). For models that benefit from soft conditioning, you can reconstruct a prompt-formatted version of each example at training time:

```python
def format_training_example(row):
    year = int(row['year']) if pd.notna(row['year']) else 'Unknown'
    header = (
        f"[Genre: {row['tag']}]\n"
        f"[Artist: {row['artist']}]\n"
        f"[Year: {year}]\n"
        f"[Title: {row['title']}]\n\n"
    )
    return header + row['lyrics']
```

This soft-conditioning format allows models to learn genre, artist, and era as implicit style tokens without hard task prefixes.

### Token Length Distribution

Based on word-count proxies measured during cleaning:
- The **majority of entries fall under 512 words**, making this dataset well-suited for models with a 512–1024 token context window.
- Setting `max_seq_length=1024` in your training configuration captures the vast majority of examples without truncation.

> **Sources:**  
> [`carlosgdcj/genius-song-lyrics-with-language-information`](https://huggingface.co/datasets/carlosgdcj/genius-song-lyrics-with-language-information) ~9+ GB (CSV)  
>[theelderemo/genius-lyrics-cleaned](https://huggingface.co/datasets/theelderemo/genius-lyrics-cleaned) ~2.56 GB

The original dataset was collected by scraping [Genius.com](https://genius.com) and includes language detection metadata alongside raw lyrics. It contains entries across many languages and content types.

### Curation

The raw dataset is large and noisy. The `misc` category alone contributes a significant portion of non-music content. Language diversity, while useful for multilingual tasks, is a source of noise for English-only modeling. This cleaned version was created specifically to provide a **high-quality, ready-to-train English lyric corpus** that does not require additional preprocessing.

### Citation

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
