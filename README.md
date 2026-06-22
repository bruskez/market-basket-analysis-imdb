# Project 2 — Market-Basket Analysis on the IMDb Top 1000 Dataset

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/bruskez/market-basket-analysis-imdb/blob/main/market_basket_analysis.ipynb)

Frequent-itemset mining applied to movie casts: each movie in the [IMDb Top 1000 dataset](https://www.kaggle.com/datasets/harshitshankhdhar/imdb-dataset-of-top-1000-movies-and-tv-shows) is treated as a *basket*, and the four lead actors (`Star1`-`Star4`) as the *items* in it. The goal is to find groups of actors that recur together across multiple films.

## What's implemented

All algorithms are implemented from scratch in Python (no frequent-itemset-mining library):

- **Apriori** — iterative frequent-itemset discovery exploiting downward-closure (monotonicity) pruning.
- **PCY** (Park-Chen-Yu) — hash-based optimization of Apriori's most expensive step (pair counting), reducing the candidate-set size.
- **Association rules** (`I -> j`, single-item consequent) with **confidence** and **interest**.

## Repository structure

```
.
├── market_basket_analysis.ipynb   # main notebook (runnable on Colab or locally)
├── report.pdf                     # full project report
├── requirements.txt               # Python dependencies (local runs only)
└── README.md
```

## Running the notebook

**Google Colab (zero setup):** click the badge above.

The notebook is fully deterministic (a fixed MD5-based hash is used for PCY instead of Python's randomized `hash()`), so re-running it — locally or on Colab — reproduces identical results.

## Report

See `report.pdf` for the full methodology, scalability analysis, and discussion of results.
