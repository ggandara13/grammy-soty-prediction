# 📓 Notebooks

Run these notebooks in order to reproduce the prediction pipeline.

## Pipeline Order

| # | Notebook | Description | Key Outputs |
|---|----------|-------------|-------------|
| 1 | `01_data_collection.ipynb` | Gather Billboard charts, lyrics from Genius, streaming data | `nominees_2026.json`, lyrics files |
| 2 | `02_lyrics_nlp.ipynb` | TF-IDF analysis, vocabulary metrics, narrative depth scoring | Lyric originality scores |
| 3 | `03_topic_modeling.ipynb` | LDA topic modeling, thematic analysis | Topic distributions, visualizations |
| 4 | `04_audio_analysis.ipynb` | Audio features (BPM, energy, valence), Grammy pedigree analysis | Audio scores, Grammy bias scores |
| 5 | `historical_winner_analysis.py` | Compare nominees to past SOTY winners (2016-2025) | `historical_winner_analysis.json` |
| 6 | `05_scoring_ensemble.ipynb` | Combine all features, calculate win probabilities | **Final prediction!** |

## Quick Start

If you just want to see the final prediction without running the full pipeline:

```bash
# Open directly - all scores are embedded
jupyter notebook 05_scoring_ensemble.ipynb
```

## Dependencies

All notebooks require:
```bash
pip install -r ../requirements.txt
```

## Notes

- Notebooks 01-04 require API access (Genius, Billboard)
- Notebook 05 can run standalone with embedded scores
- Clear outputs before committing to GitHub (smaller file sizes)
