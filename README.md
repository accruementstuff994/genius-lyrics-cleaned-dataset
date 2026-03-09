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
---
