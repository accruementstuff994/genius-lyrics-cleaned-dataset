---
dataset_info:
  features:
  - name: title
    dtype: string
  - name: artist
    dtype: string
  - name: tag
    dtype: string
  - name: year
    dtype: int64
  - name: lyrics
    dtype: string
  splits:
  - name: train
    num_bytes: 4847179321
    num_examples: 3179588
  download_size: 2558825005
  dataset_size: 4847179321
configs:
- config_name: default
  data_files:
  - split: train
    path: data/train-*
license: mit
language:
- en
pretty_name: Genius English Song Lyrics – Cleaned & Deduplicated
task_categories:
- text-generation
task_ids:
- language-modeling
tags:
- lyrics
- music
- songs
- rap
- trap
- pop
- rb
- rock
- country
- metal
- folk
- jazz
- indie
- electronic
- reggae
- soul
- blues
- english
- fine-tuning
- causal-lm
- conditional-generation
- song-generation
- creative-writing
- nlp
- cleaned
size_categories:
- 1M<n<10M
source_datasets:
- carlosgdcj/genius-song-lyrics-with-language-information
---

# Genius English Song Lyrics – Cleaned & Deduplicated

A heavily cleaned, English-only, genre-filtered subset of the [Genius Song Lyrics with Language Information](https://www.kaggle.com/datasets/carlosgdcj/genius-song-lyrics-with-language-information) Kaggle dataset. Reduced from **9+ GB to 2.56 GB** through language filtering, genre filtering, artifact removal, and deduplication. Optimized for language model fine-tuning, lyric generation, and music NLP research.

- **No train/validation/test splits**: This dataset ships as a single `train` split. You should create validation and test splits appropriate to downstream task

---

## Dataset Description

### Overview

The raw Genius dataset contains millions of song entries across dozens of languages, genres, and quality levels — including non-music content like poetry, book excerpts, and miscellaneous text tagged as `misc`. This cleaned version retains only **English-language songs from verified music genres**, with lyrics scrubbed of Genius UI artifacts, HTML residue, and duplicates. The result is a high-signal corpus suitable for causal language model pretraining or supervised fine-tuning on lyric generation tasks.

### Languages

- **English only** (`language == 'en'`)

---

## Cleaning Pipeline

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

---

## Dataset Structure

### Data Fields

| Field    | Type    | Description                                                                 |
|----------|---------|-----------------------------------------------------------------------------|
| `title`  | string  | Song title as listed on Genius                                              |
| `artist` | string  | Primary artist name                                                         |
| `tag`    | string  | Genre tag (one of 15 values; see below)                                     |
| `year`   | float64 | Release year (may be `NaN` for entries with missing metadata)              |
| `lyrics` | string  | Cleaned, deduplicated song lyrics with normalized section headers           |

### Genre Tags (`tag` column)

The dataset includes the following 15 genre values:

`rap` · `trap` · `pop` · `rb` · `rock` · `country` · `metal` · `folk` · `jazz` · `indie` · `electronic` · `reggae` · `soul` · `blues` · `latin`

## Training Format

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

---

## Token Length Distribution

Based on word-count proxies measured during cleaning:
- The **majority of entries fall under 512 words**, making this dataset well-suited for models with a 512–1024 token context window.
- Setting `max_seq_length=1024` in your training configuration captures the vast majority of examples without truncation.

---

## Source Data

### Original Dataset

- **Source**: [Genius Song Lyrics with Language Information](https://www.kaggle.com/datasets/carlosgdcj/genius-song-lyrics-with-language-information) by [carlosgdcj](https://www.kaggle.com/carlosgdcj) on Kaggle
- **Original size**: ~9+ GB (CSV)
- **Cleaned size**: ~2.56 GB

The original dataset was collected by scraping [Genius.com](https://genius.com) and includes language detection metadata alongside raw lyrics. It contains entries across many languages and content types.

### Curation Rationale

The raw dataset is large and noisy. The `misc` category alone contributes a significant portion of non-music content. Language diversity, while useful for multilingual tasks, is a source of noise for English-only modeling. This cleaned version was created specifically to provide a **high-quality, ready-to-train English lyric corpus** that does not require additional preprocessing.

---

## Dataset Card Authors

- **theelderemo** — Cleaning, filtering, and Hugging Face upload

## Dataset Card Contact

Open an issue or discussion on this repository for questions, corrections, or collaboration requests.

---

## Citation

If you use this dataset in research or a project, please cite both the upstream Kaggle source and this repository:

```bibtex
@misc{genius_lyrics_cleaned_2026,
  author       = {theelderemo},
  title        = {Genius English Song Lyrics – Cleaned \& Deduplicated},
  year         = {2026},
  publisher    = {Hugging Face},
  howpublished = {\url{https://huggingface.co/datasets/theelderemo/genius-lyrics-cleaned}},
  note         = {Derived from \url{https://www.kaggle.com/datasets/carlosgdcj/genius-song-lyrics-with-language-information}}
}