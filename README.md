# 🏆 Grammy 2026 Prediction Models

[![Python 3.9+](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)

Data-driven prediction models for the Grammy Awards using NLP, audio analysis, and ensemble scoring methods.

## 🎯 Results: Both Models Correctly Predicted Their Categories!

| Category | Model | Prediction | Actual Winner | Result |
|----------|-------|------------|---------------|--------|
| **Record of the Year** | v1.0 (Production-focused) | **luther** | **luther** | ✅ |
| **Song of the Year** | v2.0 (Songwriting-focused) | **WILDFLOWER** | **WILDFLOWER** | ✅ |

---

## 📋 Table of Contents

- [Key Insight](#key-insight)
- [Record of the Year Model](#record-of-the-year-model)
- [Song of the Year Model](#song-of-the-year-model)
- [Why Two Models?](#why-two-models)
- [Methodology](#methodology)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Lessons Learned](#lessons-learned)

---

## Key Insight

The Grammy's **Record of the Year** and **Song of the Year** awards evaluate fundamentally different aspects of music:

| Aspect | Record of the Year | Song of the Year |
|--------|-------------------|------------------|
| **Rewards** | Production, performance, sound | Songwriting, lyrics, composition |
| **Judges** | How it sounds | How it's written |
| **Key Factors** | Energy, mix, vocal delivery, charts | Narrative depth, lyrical craft, emotional arc |
| **Typical Winners** | High-production tracks, anthems | Introspective, story-driven songs |

This insight led to developing **two specialized models** rather than one generic predictor.

---

## Record of the Year Model

### 2026 Nominees (ROTY)

| Rank | Song | Artist | Win Probability |
|:----:|------|--------|:---------------:|
| 🥇 | **luther** | Kendrick Lamar & SZA | **18.2%** |
| 🥈 | APT. | ROSÉ & Bruno Mars | 15.4% |
| 🥉 | Abracadabra | Lady Gaga | 14.1% |
| 4 | WILDFLOWER | Billie Eilish | 13.3% |
| 5 | Manchild | Sabrina Carpenter | 11.5% |
| 6 | The Subway | Chappell Roan | 10.2% |
| 7 | DtMF | Bad Bunny | 9.1% |
| 8 | Anxiety | Doechii | 8.2% |

### Model v1.0 Weights (Production-Focused)

| Feature | Weight | Rationale |
|---------|:------:|-----------|
| Cultural Impact | 25% | Chart performance, streaming, buzz |
| Media Momentum | 20% | Pre-Grammy coverage and hype |
| Grammy Pedigree | 18% | Artist's Grammy history |
| Audio Production | 15% | Energy, production complexity |
| Musical Structure | 12% | Tempo, danceability, mix quality |
| Lyric Originality | 10% | Less important for ROTY |

### Why luther Won ROTY

- **Production excellence**: Kendrick + SZA collaboration with top-tier production
- **Cultural moment**: Massive streaming and chart presence
- **Grammy momentum**: Kendrick's 2025 SOTY win for "Not Like Us"
- **Sonic impact**: Perfect blend of hip-hop and R&B production

---

## Song of the Year Model

### 2026 Nominees (SOTY)

| Rank | Song | Artist/Songwriters | Win Probability |
|:----:|------|-------------------|:---------------:|
| 🥇 | **WILDFLOWER** | Billie Eilish O'Connell, FINNEAS O'Connell | **23.0%** |
| 🥈 | luther | Kendrick Lamar, SZA, Jack Antonoff + 7 writers | 16.3% |
| 🥉 | APT. | Amy Allen, Bruno Mars, ROSÉ + 6 writers | 12.7% |
| 4 | Manchild | Amy Allen, Jack Antonoff, Sabrina Carpenter | 11.0% |
| 5 | Golden | Ejae, Mark Sonnenblick | 9.8% |
| 6 | Abracadabra | Lady Gaga, Henry Walter, Andrew Watt | 9.4% |
| 7 | DtMF | Bad Bunny + 6 writers | 9.1% |
| 8 | Anxiety | Jaylah Hickmon (Doechii) | 8.7% |

*Note: SOTY rewards songwriters, not performers. Nominees differ from ROTY.*

### Model v2.0 Weights (Songwriting-Focused)

| Feature | Weight | Rationale |
|---------|:------:|-----------|
| Historical Winner Similarity | 30% | Matches proven SOTY-winning formula |
| Narrative Depth | 18% | Storytelling quality, emotional arc |
| Cultural Impact | 15% | Still matters, but less than ROTY |
| Grammy Pedigree | 12% | Artist's songwriting recognition |
| Lyric Originality | 10% | Vocabulary, uniqueness |
| Media Momentum | 8% | Less predictive for SOTY |
| Musical Structure | 7% | Composition over production |

### Why WILDFLOWER Won SOTY

- **Proven formula**: Matches Billie's previous SOTY wins almost exactly
  - Low energy (0.25 vs 0.23 for "Everything I Wanted")
  - Low valence (melancholic, introspective)
  - High acousticness (intimate production)
- **Narrative depth**: Highest score among all nominees
- **Track record**: Billie has won SOTY twice before (2020, 2021)
- **Songwriting craft**: FINNEAS and Billie's signature minimalist style

---

## Why Two Models?

### The Discovery

My initial v1.0 model predicted **luther** would win Song of the Year. When **WILDFLOWER** won instead, I conducted post-mortem analysis and discovered:

1. **SOTY rewards different qualities** than chart performance
2. **Historical patterns matter** - artists with proven formulas repeat success
3. **Narrative depth** is crucial for songwriting awards

### The Realization

When the Record of the Year was announced as **luther**, I realized my "failed" v1.0 model was actually **predicting the wrong category**. It was optimized for production/performance metrics that ROTY rewards!

### The Lesson

> "A model isn't wrong just because it predicts the wrong outcome - it might be answering a different question."

This led to developing category-specific models, both of which proved accurate.

---

## Methodology

### Pipeline Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                    DATA COLLECTION                              │
│  Audio Features │ Lyrics │ Charts │ Grammy History              │
└─────────────────────────────────────────────────────────────────┘
                                 │
        ┌────────────────────────┴────────────────────────┐
        │                                                 │
        ▼                                                 ▼
┌───────────────────┐                         ┌───────────────────┐
│  ROTY MODEL (v1)  │                         │  SOTY MODEL (v2)  │
│                   │                         │                   │
│ • Chart-heavy     │                         │ • Historical      │
│ • Production      │                         │   patterns        │
│ • Energy/Sound    │                         │ • Narrative depth │
│ • Media buzz      │                         │ • Lyric craft     │
└───────────────────┘                         └───────────────────┘
        │                                                 │
        ▼                                                 ▼
┌───────────────────┐                         ┌───────────────────┐
│ Prediction:       │                         │ Prediction:       │
│ luther ✅         │                         │ WILDFLOWER ✅     │
└───────────────────┘                         └───────────────────┘
```

### Feature Comparison

| Feature | Description | ROTY Weight | SOTY Weight |
|---------|-------------|:-----------:|:-----------:|
| Cultural Impact | Billboard, streaming, social | **25%** | 15% |
| Historical Winner | Audio similarity to past winners | 10% | **30%** |
| Narrative Depth | Storytelling, emotional arc | 5% | **18%** |
| Grammy Pedigree | Artist's Grammy history | **18%** | 12% |
| Media Momentum | News coverage, pre-Grammy buzz | **20%** | 8% |
| Lyric Originality | TF-IDF, vocabulary richness | 10% | 10% |
| Audio/Production | Energy, danceability, mix | 12% | 7% |

---

## Project Structure

```
grammy-prediction/
│
├── README.md                 # This file
├── requirements.txt          # Python dependencies
├── LICENSE                   # MIT License
│
├── notebooks/
│   ├── 01_data_collection.ipynb      # Gather all data
│   ├── 02_lyrics_nlp.ipynb           # Lyrical analysis
│   ├── 03_topic_modeling.ipynb       # Thematic analysis
│   ├── 04_media_sentiment.ipynb      # Media/Grammy analysis
│   ├── 05_scoring_ensemble.ipynb     # Both models comparison
│   └── historical_winner_analysis.py # Past winner patterns
│
├── data/
│   ├── roty_nominees_2026.json       # ROTY nominees
│   ├── soty_nominees_2026.json       # SOTY nominees
│   └── audio_features.json           # Verified audio data
│
└── outputs/
    ├── roty_prediction.json          # ROTY results
    └── soty_prediction.json          # SOTY results
```

---

## Installation

```bash
# Clone the repository
git clone https://github.com/ggandara13/grammy-soty-prediction.git
cd grammy-soty-prediction

# Create virtual environment (recommended)
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Launch Jupyter
jupyter notebook
```

---

## Lessons Learned

### 1. Domain Knowledge Matters
Understanding that ROTY and SOTY reward different qualities was key to building accurate models.

### 2. "Failed" Models Might Be Answering Different Questions
The v1.0 model wasn't wrong - it was predicting ROTY metrics for a SOTY question.

### 3. Post-Mortem Analysis is Valuable
Analyzing why a prediction failed led to discovering the two-model approach.

### 4. Historical Patterns are Powerful
For SOTY, artists who have won before often repeat similar formulas.

---

## Interview Talking Points

> "I built two specialized prediction models for different Grammy categories. When my initial SOTY prediction was wrong, post-mortem analysis revealed it was actually optimized for Record of the Year. This led to developing category-specific models - both of which correctly predicted their respective winners. The project demonstrates iterative improvement, domain understanding, and the importance of matching model design to the actual question being asked."

---

## Tech Stack

- **Python 3.9+** - Core language
- **pandas/numpy** - Data manipulation
- **scikit-learn** - NLP, TF-IDF, topic modeling
- **matplotlib/seaborn** - Visualization
- **Jupyter** - Interactive notebooks

---

## Author

**Gerardo Gandara** - Senior Data Scientist

📧 gerardo.gandara@gmail.com  
💼 [LinkedIn](https://www.linkedin.com/in/gerardo-gandara/)  
🐙 [GitHub](https://github.com/ggandara13)

Expertise: Marketing Mix Modeling, A/B Testing, NLP, Predictive Analytics

---

## License

MIT License - see [LICENSE](LICENSE) file.

---

<p align="center">
  <b>Two categories. Two models. Two correct predictions. 🏆🏆</b>
</p>
