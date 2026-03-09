<div align="center">

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 900 80" width="100%">
  <defs>
    <linearGradient id="aat-g" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%" stop-color="#7C3AED" stop-opacity="1"/>
      <stop offset="55%" stop-color="#7C3AED" stop-opacity="0.3"/>
      <stop offset="100%" stop-color="#7C3AED" stop-opacity="0"/>
    </linearGradient>
  </defs>
  <rect x="0" y="0" width="900" height="1.5" fill="url(#aat-g)"/>
  <rect x="0" y="0" width="4" height="80" fill="#7C3AED"/>
  <text x="888" y="72" font-family="Fira Code, Consolas, monospace" font-size="62" fill="#7C3AED" opacity="0.07" text-anchor="end">◎</text>
  <text x="20" y="42" font-family="Fira Code, Consolas, monospace" font-size="24" font-weight="700" fill="#e6edf3" letter-spacing="1.5">Genius Lyrics Dataset</text>
  <text x="20" y="62" font-family="Fira Code, Consolas, monospace" font-size="11" fill="#7C3AED" letter-spacing="2.5">Cleaned & Deduplicated</text>
</svg>

<div align="center">
  <a href="https://huggingface.co/datasets/theelderemo/genius-lyrics-cleaned" target="_blank" rel="noopener noreferrer">
    <svg xmlns="http://www.w3.org/2000/svg" width="110" height="20" style="margin: 0 4px 8px 0;" role="img" aria-label="🤗 Hugging Face">
      <clipPath id="clip1">
        <rect width="110" height="20" rx="3" fill="#fff"/>
      </clipPath>
      <g clip-path="url(#clip1)">
        <rect width="110" height="20" fill="#161b22"/>
      </g>
      <g fill="#fff" text-anchor="middle" font-family="Verdana,Geneva,DejaVu Sans,sans-serif" font-size="11">
        <text x="55" y="15" fill="#010101" fill-opacity=".3">🤗 Hugging Face</text>
        <text x="55" y="14">🤗 Hugging Face</text>
      </g>
    </svg>
  </a>
<svg xmlns="http://www.w3.org/2000/svg" width="140" height="20" style="margin: 0 4px 8px 0;" role="img" aria-label="DOI: 10.57967/hf/7978">
    <clipPath id="clip2">
      <rect width="140" height="20" rx="3" fill="#fff"/>
    </clipPath>
    <g clip-path="url(#clip2)">
      <rect width="140" height="20" fill="#161b22"/>
    </g>
    <g fill="#fff" text-anchor="middle" font-family="Verdana,Geneva,DejaVu Sans,sans-serif" font-size="11">
      <text x="70" y="15" fill="#010101" fill-opacity=".3">DOI: 10.57967/hf/7978</text>
      <text x="70" y="14">DOI: 10.57967/hf/7978</text>
    </g>
  </svg>
  <svg xmlns="http://www.w3.org/2000/svg" width="115" height="20" style="margin: 0 4px 8px 0;" role="img" aria-label="revision: 9742989">
    <clipPath id="clip3">
      <rect width="115" height="20" rx="3" fill="#fff"/>
    </clipPath>
    <g clip-path="url(#clip3)">
      <rect width="115" height="20" fill="#161b22"/>
    </g>
    <g fill="#fff" text-anchor="middle" font-family="Verdana,Geneva,DejaVu Sans,sans-serif" font-size="11">
      <text x="57.5" y="15" fill="#010101" fill-opacity=".3">revision: 9742989</text>
      <text x="57.5" y="14">revision: 9742989</text>
    </g>
  </svg>
</div>

A heavily cleaned, English-only, genre-filtered subset of the [Genius Song Lyrics with Language Information](https://www.kaggle.com/datasets/carlosgdcj/genius-song-lyrics-with-language-information) Kaggle dataset. Reduced from **9+ GB to 2.56 GB** through language filtering, genre filtering, artifact removal, and deduplication. Optimized for language model fine-tuning, lyric generation, and music NLP research.  

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 50" width="100%">
    <line x1="0" y1="0" x2="800" y2="0" stroke="#cc0033" stroke-width="2"/>
</svg>  
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 50" width="100%">
    <text x="400" y="34" font-family="Fira Code, Consolas, monospace" font-size="32" font-weight="700" fill="#e6edf3" letter-spacing="2" text-anchor="middle">No train/validation/test splits</text>
</svg>

This dataset ships as a single `train` split. You should create validation and test splits appropriate to downstream task  

<br>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 50" width="100%">
  <line x1="0" y1="0" x2="800" y2="0" stroke="#cc0033" stroke-width="2"/>
  <text x="400" y="34" font-family="Fira Code, Consolas, monospace" font-size="32" font-weight="700" fill="#e6edf3" letter-spacing="2" text-anchor="middle">Overview</text>
  <line x1="0" y1="48" x2="800" y2="48" stroke="#cc0033" stroke-width="4"/>
</svg>  

<br>

The raw Genius dataset contains millions of song entries across dozens of languages, genres, and quality levels — including non-music content like poetry, book excerpts, and miscellaneous text tagged as `misc`. This cleaned version retains only **English-language songs from verified music genres**, with lyrics scrubbed of Genius UI artifacts, HTML residue, and duplicates. The result is a high-signal corpus suitable for causal language model pretraining or supervised fine-tuning on lyric generation tasks.

</svg>  
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 50" width="100%">
    <text x="400" y="34" font-family="Fira Code, Consolas, monospace" font-size="32" font-weight="700" fill="#e6edf3" letter-spacing="2" text-anchor="middle">Dataset Stats</text>
    <line x1="0" y1="48" x2="800" y2="48" stroke="#cc0033" stroke-width="2"/>
</svg>

<br>  

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 332" width="100%">
  <defs>
    <style>
      .th { font-family: Fira Code, Consolas, monospace; font-size: 13px; font-weight: 700; fill: #e6edf3; }
      .td-label { font-family: Fira Code, Consolas, monospace; font-size: 12px; fill: #e6edf3; }
      .td-value { font-family: Fira Code, Consolas, monospace; font-size: 12px; fill: #e6edf3; }
    </style>
  </defs>
  <!-- header row -->
  <rect x="0" y="0" width="800" height="28" rx="4" fill="#7C3AED" opacity="0.12"/>
  <text x="20" y="19" class="th">Metric</text>
  <text x="320" y="19" class="th">Value</text>
  <line x1="0" y1="28" x2="800" y2="28" stroke="#7C3AED" stroke-opacity="0.3" stroke-width="1"/>
  <!-- rows -->
  <text x="20"  y="52"  class="td-label">Total rows</text>
  <text x="320" y="52"  class="td-value">3,179,588</text>
  <line x1="0" y1="60" x2="800" y2="60" stroke="#30363d" stroke-width="0.5"/>
  <text x="20"  y="82"  class="td-label">Dataset size</text>
  <text x="320" y="82"  class="td-value">~4.51 GB</text>
  <line x1="0" y1="90" x2="800" y2="90" stroke="#30363d" stroke-width="0.5"/>
  <text x="20"  y="112" class="td-label">Download size</text>
  <text x="320" y="112" class="td-value">~2.38 GB</text>
  <line x1="0" y1="120" x2="800" y2="120" stroke="#30363d" stroke-width="0.5"/>
  <text x="20"  y="142" class="td-label">Split</text>
  <text x="320" y="142" class="td-value">train only</text>
  <line x1="0" y1="150" x2="800" y2="150" stroke="#30363d" stroke-width="0.5"/>
  <text x="20"  y="172" class="td-label">Path</text>
  <text x="320" y="172" class="td-value">data/train-*</text>
  <line x1="0" y1="180" x2="800" y2="180" stroke="#30363d" stroke-width="0.5"/>
  <text x="20"  y="202" class="td-label">num_bytes</text>
  <text x="320" y="202" class="td-value">4847179321</text>
  <line x1="0" y1="210" x2="800" y2="210" stroke="#30363d" stroke-width="0.5"/>
  <text x="20"  y="232" class="td-label">num_examples</text>
  <text x="320" y="232" class="td-value">3179588</text>
  <line x1="0" y1="240" x2="800" y2="240" stroke="#30363d" stroke-width="0.5"/>
  <text x="20"  y="262" class="td-label">task_categories</text>
  <text x="320" y="262" class="td-value">text-generation</text>
  <line x1="0" y1="270" x2="800" y2="270" stroke="#30363d" stroke-width="0.5"/>
  <text x="20"  y="292" class="td-label">task_ids</text>
  <text x="320" y="292" class="td-value">language-modeling</text>
  <line x1="0" y1="300" x2="800" y2="300" stroke="#30363d" stroke-width="0.5"/>
  <text x="20"  y="322" class="td-label">size_categories</text>
  <text x="320" y="322" class="td-value">1M&lt;n&lt;10M</text>
  <line x1="0" y1="332" x2="800" y2="332" stroke="#7C3AED" stroke-opacity="0.3" stroke-width="1"/>
</svg>

<br>

</svg>  
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 50" width="100%">
    <text x="400" y="34" font-family="Fira Code, Consolas, monospace" font-size="32" font-weight="700" fill="#e6edf3" letter-spacing="2" text-anchor="middle">Cleaning Pipeline</text>
    <line x1="0" y1="48" x2="800" y2="48" stroke="#cc0033" stroke-width="2"/>
</svg>  

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

<br >
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 50" width="100%">
    <text x="400" y="34" font-family="Fira Code, Consolas, monospace" font-size="32" font-weight="700" fill="#e6edf3" letter-spacing="2" text-anchor="middle">Data Structure</text>
        <line x1="0" y1="48" x2="800" y2="48" stroke="#cc0033" stroke-width="2"/>
</svg>  

<br>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 182" width="100%">
  <defs>
    <style>
      .ds-th { font-family: Fira Code, Consolas, monospace; font-size: 13px; font-weight: 700; fill: #7C3AED; }
      .ds-label { font-family: Fira Code, Consolas, monospace; font-size: 12px; fill: #e6edf3; }
      .ds-type { font-family: Fira Code, Consolas, monospace; font-size: 12px; fill: #7C3AED; }
      .ds-desc { font-family: Fira Code, Consolas, monospace; font-size: 11px; fill: #8b949e; }
    </style>
  </defs>
  <rect x="0" y="0" width="800" height="28" rx="4" fill="#7C3AED" opacity="0.12"/>
  <text x="20" y="19" class="ds-th">Field</text>
  <text x="140" y="19" class="ds-th">Type</text>
  <text x="280" y="19" class="ds-th">Description</text>
  <line x1="0" y1="28" x2="800" y2="28" stroke="#7C3AED" stroke-opacity="0.3" stroke-width="1"/>
  <text x="20"  y="52"  class="ds-label">title</text>
  <text x="140" y="52"  class="ds-type">string</text>
  <text x="280" y="52"  class="ds-desc">Song title as listed on Genius</text>
  <line x1="0" y1="60" x2="800" y2="60" stroke="#30363d" stroke-width="0.5"/>
  <text x="20"  y="82"  class="ds-label">artist</text>
  <text x="140" y="82"  class="ds-type">string</text>
  <text x="280" y="82"  class="ds-desc">Primary artist name</text>
  <line x1="0" y1="90" x2="800" y2="90" stroke="#30363d" stroke-width="0.5"/>
  <text x="20"  y="112" class="ds-label">tag</text>
  <text x="140" y="112" class="ds-type">string</text>
  <text x="280" y="112" class="ds-desc">Genre tag (one of 15 values; see below)</text>
  <line x1="0" y1="120" x2="800" y2="120" stroke="#30363d" stroke-width="0.5"/>
  <text x="20"  y="142" class="ds-label">year</text>
  <text x="140" y="142" class="ds-type">float64</text>
  <text x="280" y="142" class="ds-desc">Release year (may be NaN for entries with missing metadata)</text>
  <line x1="0" y1="150" x2="800" y2="150" stroke="#30363d" stroke-width="0.5"/>
  <text x="20"  y="172" class="ds-label">lyrics</text>
  <text x="140" y="172" class="ds-type">string</text>
  <text x="280" y="172" class="ds-desc">Cleaned, deduplicated lyrics with normalized section headers</text>
  <line x1="0" y1="182" x2="800" y2="182" stroke="#7C3AED" stroke-opacity="0.3" stroke-width="1"/>
</svg>

<br>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 60" width="100%">
  <text x="400" y="16" font-family="Fira Code, Consolas, monospace" font-size="12" fill="#8b949e" text-anchor="middle">The dataset includes the following 15 genre values:</text>
  <text x="400" y="46" font-family="Fira Code, Consolas, monospace" font-size="13" fill="#7C3AED" text-anchor="middle">rap · trap · pop · rb · rock · country · metal · folk · jazz · indie · electronic · reggae · soul · blues · latin</text>
</svg>

<br>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 50" width="100%">
  <text x="400" y="34" font-family="Fira Code, Consolas, monospace" font-size="32" font-weight="700" fill="#e6edf3" letter-spacing="2" text-anchor="middle">Training Format</text>
  <line x1="0" y1="48" x2="800" y2="48" stroke="#cc0033" stroke-width="2"/>
</svg>

<br>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 48" width="100%">
  <text x="0" y="16" font-family="Fira Code, Consolas, monospace" font-size="13" fill="#e6edf3">Each row's lyrics field contains plain cleaned lyrics with normalized section headers</text>
  <text x="0" y="36" font-family="Fira Code, Consolas, monospace" font-size="13" fill="#e6edf3">([Verse 1], [Chorus], [Bridge], etc.). For models that benefit from soft conditioning,</text>
  <text x="0" y="48" font-family="Fira Code, Consolas, monospace" font-size="13" fill="#e6edf3">you can reconstruct a prompt-formatted version of each example at training time:</text>
</svg>

<br>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 210" width="100%">
  <rect x="0" y="0" width="800" height="210" rx="6" fill="#161b22"/>
  <rect x="0" y="0" width="800" height="24" rx="6" fill="#1c2129"/>
  <rect x="0" y="12" width="800" height="12" fill="#1c2129"/>
  <circle cx="16" cy="12" r="5" fill="#cc0033" opacity="0.8"/>
  <circle cx="34" cy="12" r="5" fill="#e6a700" opacity="0.8"/>
  <circle cx="52" cy="12" r="5" fill="#3fb950" opacity="0.8"/>
  <text x="780" y="16" font-family="Fira Code, Consolas, monospace" font-size="10" fill="#8b949e" text-anchor="end">python</text>
  <text x="20" y="46"  font-family="Fira Code, Consolas, monospace" font-size="12" fill="#ff7b72">def</text>
  <text x="50" y="46"  font-family="Fira Code, Consolas, monospace" font-size="12" fill="#d2a8ff">format_training_example</text>
  <text x="226" y="46" font-family="Fira Code, Consolas, monospace" font-size="12" fill="#e6edf3">(row):</text>
  <text x="40" y="66"  font-family="Fira Code, Consolas, monospace" font-size="12" fill="#e6edf3">year = </text>
  <text x="100" y="66" font-family="Fira Code, Consolas, monospace" font-size="12" fill="#79c0ff">int</text>
  <text x="124" y="66" font-family="Fira Code, Consolas, monospace" font-size="12" fill="#e6edf3">(row[</text>
  <text x="160" y="66" font-family="Fira Code, Consolas, monospace" font-size="12" fill="#a5d6ff">'year'</text>
  <text x="206" y="66" font-family="Fira Code, Consolas, monospace" font-size="12" fill="#e6edf3">]) </text>
  <text x="224" y="66" font-family="Fira Code, Consolas, monospace" font-size="12" fill="#ff7b72">if</text>
  <text x="244" y="66" font-family="Fira Code, Consolas, monospace" font-size="12" fill="#e6edf3"> pd.notna(row[</text>
  <text x="352" y="66" font-family="Fira Code, Consolas, monospace" font-size="12" fill="#a5d6ff">'year'</text>
  <text x="398" y="66" font-family="Fira Code, Consolas, monospace" font-size="12" fill="#e6edf3">]) </text>
  <text x="416" y="66" font-family="Fira Code, Consolas, monospace" font-size="12" fill="#ff7b72">else</text>
  <text x="452" y="66" font-family="Fira Code, Consolas, monospace" font-size="12" fill="#a5d6ff"> 'Unknown'</text>
  <text x="40" y="86"  font-family="Fira Code, Consolas, monospace" font-size="12" fill="#e6edf3">header = (</text>
  <text x="60" y="106" font-family="Fira Code, Consolas, monospace" font-size="12" fill="#a5d6ff">f"[Genre: {row['tag']}]\n"</text>
  <text x="60" y="126" font-family="Fira Code, Consolas, monospace" font-size="12" fill="#a5d6ff">f"[Artist: {row['artist']}]\n"</text>
  <text x="60" y="146" font-family="Fira Code, Consolas, monospace" font-size="12" fill="#a5d6ff">f"[Year: {year}]\n"</text>
  <text x="60" y="166" font-family="Fira Code, Consolas, monospace" font-size="12" fill="#a5d6ff">f"[Title: {row['title']}]\n\n"</text>
  <text x="40" y="186" font-family="Fira Code, Consolas, monospace" font-size="12" fill="#e6edf3">)</text>
  <text x="40" y="202" font-family="Fira Code, Consolas, monospace" font-size="12" fill="#ff7b72">return</text>
  <text x="90" y="202" font-family="Fira Code, Consolas, monospace" font-size="12" fill="#e6edf3">header + row[</text>
  <text x="192" y="202" font-family="Fira Code, Consolas, monospace" font-size="12" fill="#a5d6ff">'lyrics'</text>
  <text x="248" y="202" font-family="Fira Code, Consolas, monospace" font-size="12" fill="#e6edf3">]</text>
</svg>

<br>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 20" width="100%">
  <text x="0" y="14" font-family="Fira Code, Consolas, monospace" font-size="13" fill="#8b949e">This soft-conditioning format allows models to learn genre, artist, and era as implicit style tokens without hard task prefixes.</text>
</svg>

<br>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 50" width="100%">
  <text x="400" y="34" font-family="Fira Code, Consolas, monospace" font-size="32" font-weight="700" fill="#e6edf3" letter-spacing="2" text-anchor="middle">Token Length Distribution</text>
  <line x1="0" y1="48" x2="800" y2="48" stroke="#cc0033" stroke-width="2"/>
</svg>

<br>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 56" width="100%">
  <text x="0" y="16" font-family="Fira Code, Consolas, monospace" font-size="13" fill="#e6edf3">Based on word-count proxies measured during cleaning:</text>
  <text x="14" y="36" font-family="Fira Code, Consolas, monospace" font-size="12" fill="#8b949e">• The majority of entries fall under 512 words, well-suited for 512–1024 token context windows.</text>
  <text x="14" y="52" font-family="Fira Code, Consolas, monospace" font-size="12" fill="#8b949e">• Setting max_seq_length=1024 captures the vast majority of examples without truncation.</text>
</svg>

<br>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 50" width="100%">
  <text x="400" y="34" font-family="Fira Code, Consolas, monospace" font-size="32" font-weight="700" fill="#e6edf3" letter-spacing="2" text-anchor="middle">Sources</text>
  <line x1="0" y1="48" x2="800" y2="48" stroke="#cc0033" stroke-width="2"/>
</svg>

<br>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 72" width="100%">
  <rect x="0" y="0" width="4" height="72" fill="#7C3AED" opacity="0.5"/>
  <text x="20" y="20" font-family="Fira Code, Consolas, monospace" font-size="12" fill="#7C3AED">carlosgdcj/genius-song-lyrics-with-language-information</text>
  <text x="20" y="36" font-family="Fira Code, Consolas, monospace" font-size="11" fill="#8b949e">~9+ GB (CSV) — Original Kaggle dataset with language detection metadata</text>
  <text x="20" y="56" font-family="Fira Code, Consolas, monospace" font-size="12" fill="#7C3AED">theelderemo/genius-lyrics-cleaned</text>
  <text x="20" y="72" font-family="Fira Code, Consolas, monospace" font-size="11" fill="#8b949e">~2.56 GB — Cleaned, English-only, genre-filtered subset</text>
</svg>

<br>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 20" width="100%">
  <text x="0" y="14" font-family="Fira Code, Consolas, monospace" font-size="13" fill="#8b949e">The original dataset was collected by scraping Genius.com and includes language detection metadata alongside raw lyrics.</text>
</svg>

<br>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 50" width="100%">
  <text x="400" y="34" font-family="Fira Code, Consolas, monospace" font-size="32" font-weight="700" fill="#e6edf3" letter-spacing="2" text-anchor="middle">Curation</text>
  <line x1="0" y1="48" x2="800" y2="48" stroke="#cc0033" stroke-width="2"/>
</svg>

<br>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 56" width="100%">
  <text x="0" y="16" font-family="Fira Code, Consolas, monospace" font-size="13" fill="#e6edf3">The raw dataset is large and noisy. The misc category alone contributes a significant portion of</text>
  <text x="0" y="36" font-family="Fira Code, Consolas, monospace" font-size="13" fill="#e6edf3">non-music content. Language diversity, while useful for multilingual tasks, is a source of noise for</text>
  <text x="0" y="52" font-family="Fira Code, Consolas, monospace" font-size="13" fill="#e6edf3">English-only modeling. This cleaned version provides a high-quality, ready-to-train English lyric corpus.</text>
</svg>

<br>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 50" width="100%">
  <text x="400" y="34" font-family="Fira Code, Consolas, monospace" font-size="32" font-weight="700" fill="#e6edf3" letter-spacing="2" text-anchor="middle">Citation</text>
  <line x1="0" y1="48" x2="800" y2="48" stroke="#cc0033" stroke-width="2"/>
</svg>

<br>

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