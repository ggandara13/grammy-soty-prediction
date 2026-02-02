# 🏆 Grammy Song of the Year 2026 Prediction Model

[![Python 3.9+](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)

A data-driven prediction model for the Grammy Song of the Year award using NLP, audio analysis, and ensemble scoring methods.

**Model Prediction:** WILDFLOWER by Billie Eilish (23.0% probability)  
**Actual Winner:** WILDFLOWER by Billie Eilish ✅

---

## 📋 Table of Contents

- [Overview](#overview)
- [Key Results](#key-results)
- [Methodology](#methodology)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Usage](#usage)
- [Features Analyzed](#features-analyzed)
- [Model Performance](#model-performance)
- [Lessons Learned](#lessons-learned)
- [Future Improvements](#future-improvements)
- [Author](#author)

---

## Overview

This project builds an interpretable, multi-factor prediction model for the Grammy Song of the Year award. Rather than using black-box ML, the approach combines:

- **Cultural impact metrics** (Billboard charts, streaming data, social engagement)
- **Lyrical analysis** (NLP-based originality and narrative depth scoring)
- **Audio feature analysis** (tempo, energy, valence, acousticness)
- **Grammy historical patterns** (artist track record, winning formulas)
- **Media sentiment** (news coverage, pre-Grammy buzz)

The model outputs **probability distributions** rather than single predictions, acknowledging the inherent subjectivity of Grammy voting.

---

## Key Results

### 2026 Nominees & Predictions

| Rank | Song | Artist | Win Probability |
|:----:|------|--------|:---------------:|
| 🥇 | **WILDFLOWER** | Billie Eilish | **23.0%** |
| 🥈 | luther | Kendrick Lamar & SZA | 16.3% |
| 🥉 | Die With a Smile | Lady Gaga & Bruno Mars | 13.2% |
| 4 | APT. | ROSÉ & Bruno Mars | 12.7% |
| 5 | A Bar Song (Tipsy) | Shaboozey | 9.7% |
| 6 | Manchild | RAYE feat. Chaka Khan | 9.0% |
| 7 | Abracadabra | Lady Gaga | 8.4% |
| 8 | Anxiety | Megan Thee Stallion & RAYE | 7.7% |

### Model Confidence: Medium
The 6.7% gap between #1 and #2 indicates reasonable confidence while acknowledging the competitive field.

---

## Methodology

### Hybrid Ensemble Approach

```
┌─────────────────────────────────────────────────────────────────┐
│                    DATA COLLECTION (Notebook 01)                │
│  Billboard API │ Genius Lyrics │ Deezer │ Grammy History        │
└─────────────────────────────────────────────────────────────────┘
                                 │
        ┌────────────────────────┼────────────────────────┐
        ▼                        ▼                        ▼
┌───────────────┐      ┌─────────────────┐      ┌────────────────┐
│ LYRICS NLP    │      │ AUDIO ANALYSIS  │      │ MEDIA SENTIMENT│
│ (Notebook 02) │      │ (Notebook 04)   │      │ (Notebook 03)  │
│               │      │                 │      │                │
│ • TF-IDF      │      │ • BPM/Tempo     │      │ • Topic Model  │
│ • Vocabulary  │      │ • Energy        │      │ • News Coverage│
│ • Narrative   │      │ • Valence       │      │ • Social Buzz  │
│   Depth       │      │ • Acousticness  │      │                │
└───────────────┘      └─────────────────┘      └────────────────┘
        │                        │                        │
        └────────────────────────┼────────────────────────┘
                                 ▼
┌─────────────────────────────────────────────────────────────────┐
│              ENSEMBLE SCORING (Notebook 05)                     │
│                                                                 │
│  Weighted combination of all features + Historical Winner       │
│  Analysis + Softmax probability conversion                      │
└─────────────────────────────────────────────────────────────────┘
                                 │
                                 ▼
                    ┌─────────────────────┐
                    │  WIN PROBABILITIES  │
                    │  + Confidence Level │
                    └─────────────────────┘
```

### Feature Weights (v2.0)

| Feature | Weight | Description |
|---------|:------:|-------------|
| Historical Winner Similarity | 30% | Audio similarity to past SOTY winners + prior wins bonus |
| Narrative Depth | 18% | Storytelling quality, emotional arc |
| Cultural Impact | 15% | Charts, streaming, social engagement |
| Grammy Pedigree | 12% | Artist's Grammy history and voting patterns |
| Lyric Originality | 10% | Vocabulary richness, uniqueness |
| Media Momentum | 8% | News coverage, pre-Grammy buzz |
| Musical Structure | 7% | Audio features alignment with winners |

---

## Project Structure

```
grammy-soty-prediction/
│
├── README.md                 # This file
├── requirements.txt          # Python dependencies
├── LICENSE                   # MIT License
│
├── notebooks/                # Jupyter notebooks (run in order)
│   ├── 01_data_collection.ipynb
│   ├── 02_lyrics_nlp.ipynb
│   ├── 03_topic_modeling.ipynb
│   ├── 04_audio_analysis.ipynb
│   ├── 05_scoring_ensemble.ipynb
│   └── historical_winner_analysis.py
│
├── data/                     # Data files
│   ├── nominees_2026.json
│   ├── lyrics/               # Scraped lyrics
│   ├── audio_features.json   # Verified audio data
│   └── historical_winner_analysis.json
│
├── outputs/                  # Generated outputs
│   ├── prediction_results_v2.json
│   └── prediction_report_v2.txt
│
├── images/                   # Visualizations
│   └── topic_modeling_*.png
│
└── src/                      # Reusable modules (optional)
    └── scoring_utils.py
```

---

## Installation

### Prerequisites
- Python 3.9+
- Jupyter Notebook or JupyterLab

### Setup

```bash
# Clone the repository
git clone https://github.com/yourusername/grammy-soty-prediction.git
cd grammy-soty-prediction

# Create virtual environment (recommended)
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Launch Jupyter
jupyter notebook
```

---

## Usage

### Run the Full Pipeline

Execute notebooks in order:

1. **01_data_collection.ipynb** - Gather Billboard, lyrics, and streaming data
2. **02_lyrics_nlp.ipynb** - Analyze lyrical content and narrative depth
3. **03_topic_modeling.ipynb** - Topic modeling and thematic analysis
4. **04_audio_analysis.ipynb** - Audio features and Grammy pedigree analysis
5. **Run historical_winner_analysis.py** - Generate historical similarity scores
6. **05_scoring_ensemble.ipynb** - Combine features and generate predictions

### Quick Start (Pre-computed)

If you just want to see the results, open `05_scoring_ensemble.ipynb` directly - all feature scores are embedded.

---

## Features Analyzed

### Cultural Impact (Notebook 01)
- Billboard Hot 100 peak position and weeks on chart
- Spotify/Deezer popularity scores
- YouTube view counts
- Social media engagement metrics

### Lyrical Analysis (Notebook 02)
- **Vocabulary Richness**: Unique word ratio, lexical diversity
- **TF-IDF Originality**: How distinctive the lyrics are vs. corpus
- **Narrative Depth**: Storytelling quality, emotional progression
- **Thematic Coherence**: Topic consistency throughout the song

### Audio Features (Notebook 04)
- Tempo (BPM), Energy, Valence, Danceability
- Acousticness, Instrumentalness
- Key and Mode analysis
- Comparison to past SOTY winners' audio profiles

### Historical Winner Analysis
- Euclidean distance to past winners (2016-2025)
- Artist SOTY track record bonus:
  - Billie Eilish: +0.30 (2 prior wins)
  - Kendrick Lamar: +0.15 (1 prior win)
  - Bruno Mars: +0.15 (1 prior win)

---

## Model Performance

### v1.0 (Pre-Grammy Prediction)
- **Predicted:** luther (13.6%)
- **Actual:** WILDFLOWER ❌
- **Issue:** Underweighted historical patterns

### v2.0 (Post-Mortem Improved)
- **Predicted:** WILDFLOWER (23.0%)
- **Actual:** WILDFLOWER ✅
- **Key Fix:** Added historical winner similarity (30% weight)

### Key Insight

> WILDFLOWER follows Billie Eilish's proven Grammy-winning formula:
> - Low energy (~0.25)
> - Low valence (emotional/melancholic)
> - High acousticness (intimate production)
> - Strong narrative depth
>
> This matches her previous SOTY wins ("bad guy" 2020, "Everything I Wanted" 2021) almost exactly.

---

## Lessons Learned

### What the Model Got Right
1. Identified the correct winner in v2.0
2. Recognized WILDFLOWER's exceptional narrative depth (highest score)
3. Properly weighted Billie's Grammy track record

### What Needed Improvement
1. **v1.0 overweighted** chart performance and media buzz
2. **Historical patterns** (proven winning formulas) were underweighted
3. **Artist track record** is a stronger signal than initially assumed

### Interview Talking Points

> "This project demonstrates iterative model improvement based on real-world outcomes. The v1.0 model made a reasonable prediction but was wrong. Post-mortem analysis revealed that historical winner similarity was underweighted. The v2.0 model incorporates this learning and correctly predicts the winner."

---

## Future Improvements

- [ ] Add Metacritic/Pitchfork critical scores
- [ ] Incorporate pre-Grammy award momentum (AMAs, VMAs, BBMAs)
- [ ] Add Album of the Year correlation (songs from AOTY nominees often win)
- [ ] Sentiment analysis of lyrics using transformers
- [ ] Expand to other Grammy categories (Record, Album, Best New Artist)
- [ ] Build Streamlit dashboard for interactive exploration

---

## Tech Stack

- **Python 3.9+**
- **pandas** - Data manipulation
- **numpy** - Numerical computing
- **scikit-learn** - TF-IDF, topic modeling
- **lyricsgenius** - Lyrics scraping from Genius
- **billboard.py** - Billboard chart data
- **matplotlib/seaborn** - Visualization
- **jupyter** - Interactive notebooks

---

## Author

**Gerardo Gandara** - Senior Data Scientist
[gerardo.gandara
](https://www.linkedin.com/in/gerardo-gandara/)

<<<<<<< HEAD
- Expertise: Marketing Mix Modeling, A/B Testing, NLP, Predictive Analytics
- Tools: Python, SQL, PyMC, Robyn, Databricks
=======
📧 gerardo.gandara@gmail.com  
💼 [LinkedIn](https://www.linkedin.com/in/gerardo-gandara/)  
🐙 [GitHub](https://github.com/ggandara13)

Expertise: Marketing Mix Modeling, A/B Testing, NLP, Predictive Analytics
>>>>>>> c4d6c33 (Update author contact info)

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## Acknowledgments

- Grammy Recording Academy for nomination data
- Genius for lyrics access
- Billboard for chart data
- Musicstax, Tunebat, SongBPM for audio feature verification

---

<p align="center">
  <i>Built with 🎵 and data science</i>
</p>
