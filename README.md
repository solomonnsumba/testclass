# testclass: Neural Networks in Keras

| File | What it is |
|---|---|
| `keras_intro_nba.ipynb` | Lecture notebook: intro to Keras on NBA rookie data, plus the **Bank Marketing assignment brief**. Executed. |
| `bank_marketing_solution.ipynb` | Reference solution to the assignment (Parts 1–5). Executed, with interpretations and business memo. |
| `data/nba.csv` | NBA rookie dataset (1,340 players, `TARGET_5Yrs`), from the public [pycaret datasets](https://github.com/pycaret/datasets) copy. |
| `results/` | Figures (`p3_*`, `p4_*`, `p5_*`) and `metrics.json` produced by the solution notebook. |

The bank data (UCI *Bank Marketing*, `bank-additional-full.csv`) is downloaded automatically by the solution notebook into `data/` and is not committed.

## Headline results (validation selection, single test evaluation)

| Model | Val ROC-AUC |
|---|---|
| Logistic regression | 0.802 |
| NN, linear hidden layers (selected NN) | 0.800 |
| Large NN + Dropout + EarlyStopping | 0.795 |
| Base NN 32-16 ReLU, 50 epochs (overfit) | 0.773 |

Test ROC-AUC of the selected model: **0.799**. If we call the top 1,000 of the 8,236 test customers, 475 subscribe (47.5% hit rate), against about 113 from random calling.

## Running

Executed with TensorFlow 2.21 / Keras 3 on CPU (`CUDA_VISIBLE_DEVICES=-1`). Run from the repo root:

```bash
jupyter nbconvert --to notebook --execute --inplace keras_intro_nba.ipynb bank_marketing_solution.ipynb
```

In Colab, upload `data/nba.csv` or adjust the `filename` in the intro notebook.
