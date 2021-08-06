# How Many Neighbours for Known-item Search?
This repository contains dataset and experiments for paper:
- Lokoč, J. & Souček, T. (2021). How Many Neighbours for Known-item Search?

  In Proceedings of 14th International Conference on Similarity Search and Applications, SISAP 2021

## Data
Stored in raw byte format in *data* folder with the following shapes and types:

| File                  | Data Type | Shape      |
| :---                  | :---:     | :---:      |
| data/bert_dataset.bin | float16   | 20000x2048 |
| data/bert_queries.bin | float16   | 327x2048   |
| data/clip_dataset.bin | float16   | 20000x640  |
| data/clip_queries.bin | float16   | 327x640    |
| data/targets.bin      | int32     | 327        |

- *targets.bin* contains for each query the index of the target vector in the dataset, indexed from 0.
- Other files contain unnormalized feature vectors in float16 precision in order to save space.

Read data in Python:
```python
???_dataset = np.frombuffer(open("data/???_dataset.bin", "rb").read(), dtype=np.float16).reshape(20000, -1)
???_queries = np.frombuffer(open("data/???_queries.bin", "rb").read(), dtype=np.float16).reshape(327, -1)
targets = np.frombuffer(open("data/targets.bin", "rb").read(), dtype=np.int32)
```

## Experiments
See *experiments.ipynb*.

