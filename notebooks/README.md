# 📓 Notebooks

Run these notebooks in order to reproduce the prediction pipeline.

## Pipeline

| # | Notebook | Description |
|---|----------|-------------|
| 1 | `01_data_collection.ipynb` | Gather audio features, charts, Grammy context |
| 2 | `02_lyrics_nlp.ipynb` | TF-IDF analysis, vocabulary metrics |
| 3 | `03_topic_modeling.ipynb` | LDA topic modeling, thematic analysis |
| 4 | `04_media_sentiment.ipynb` | Media coverage, Grammy pedigree |
| 5 | `05_scoring_ensemble.ipynb` | **Both models: ROTY v1.0 + SOTY v2.0** |

## Key Notebook: 05_scoring_ensemble.ipynb

This notebook demonstrates the core insight of the project:

- **Model v1.0** → Predicts **Record of the Year** (luther ✅)
- **Model v2.0** → Predicts **Song of the Year** (WILDFLOWER ✅)

Different weights for different categories!

## Quick Start

```bash
jupyter notebook 05_scoring_ensemble.ipynb
```

All scores are embedded - runs standalone without dependencies.
