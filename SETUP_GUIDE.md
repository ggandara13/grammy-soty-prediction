# 📤 GitHub Setup Guide

Follow these steps to upload this project to GitHub.

---

## Step 1: Prepare Your Notebooks

You have HTML exports of your notebooks. To get clean `.ipynb` files:

### Option A: Re-export from Jupyter (Recommended)
1. Open each notebook in Jupyter
2. Go to **File → Download as → Notebook (.ipynb)**
3. Save with clean names:
   - `01_data_collection.ipynb`
   - `02_lyrics_nlp.ipynb`
   - `03_topic_modeling.ipynb`
   - `04_audio_analysis.ipynb`
   - `05_scoring_ensemble.ipynb`

### Option B: Clear Outputs Before Uploading
1. In Jupyter: **Kernel → Restart & Clear Output**
2. Save the notebook
3. This reduces file size and removes potentially sensitive data

---

## Step 2: Create GitHub Repository

1. Go to [github.com](https://github.com) and sign in
2. Click **"New"** (green button) or go to `github.com/new`
3. Fill in:
   - **Repository name:** `grammy-soty-prediction`
   - **Description:** "Data-driven Grammy Song of the Year prediction model"
   - **Public** (recommended for portfolio)
   - ✅ **Add a README file** (NO - we have our own)
   - ✅ **Add .gitignore** (NO - we have our own)
   - **License:** MIT
4. Click **Create repository**

---

## Step 3: Upload Files

### Method A: GitHub Web Interface (Easiest)

1. In your new repo, click **"Add file" → "Upload files"**
2. Drag and drop all files from the project folder
3. Add commit message: "Initial commit - Grammy SOTY prediction model"
4. Click **"Commit changes"**

### Method B: Git Command Line (Professional)

```bash
# Clone your empty repo
git clone https://github.com/YOUR_USERNAME/grammy-soty-prediction.git
cd grammy-soty-prediction

# Copy all project files into this folder
# (README.md, requirements.txt, notebooks/, data/, etc.)

# Stage all files
git add .

# Commit
git commit -m "Initial commit - Grammy SOTY prediction model"

# Push to GitHub
git push origin main
```

---

## Step 4: Verify Structure

Your GitHub repo should look like:

```
grammy-soty-prediction/
├── README.md              ✅
├── requirements.txt       ✅
├── LICENSE                ✅
├── .gitignore             ✅
├── SETUP_GUIDE.md         (optional, can delete after setup)
│
├── notebooks/
│   ├── 01_data_collection.ipynb
│   ├── 02_lyrics_nlp.ipynb
│   ├── 03_topic_modeling.ipynb
│   ├── 04_audio_analysis.ipynb
│   ├── 05_scoring_ensemble.ipynb
│   └── historical_winner_analysis.py
│
├── data/
│   ├── nominees_2026.json
│   ├── audio_features.json
│   └── historical_winner_analysis.json
│
├── outputs/
│   ├── prediction_results_v2.json
│   └── prediction_report_v2.txt
│
└── images/
    └── (any visualizations)
```

---

## Step 5: Add Topics/Tags (Optional but Recommended)

1. On your repo page, click ⚙️ **Settings** (gear icon near "About")
2. Add topics: `data-science`, `python`, `machine-learning`, `nlp`, `grammy`, `music-analysis`, `prediction`
3. Add a website URL if you have one

---

## Step 6: Pin to Your Profile (Portfolio)

1. Go to your GitHub profile page
2. Click **"Customize your pins"**
3. Select `grammy-soty-prediction`
4. Now it appears prominently on your profile!

---

## Tips for Interviews

When sharing this project:

1. **Direct link:** `github.com/YOUR_USERNAME/grammy-soty-prediction`
2. **Talking points:**
   - "I built an interpretable prediction model using ensemble methods"
   - "The v1 model was wrong, so I did post-mortem analysis and improved it"
   - "Uses NLP for lyrics analysis, audio feature engineering, and historical pattern recognition"
   - "Demonstrates iterative model improvement based on real-world outcomes"

---

## Troubleshooting

### "File too large" error
- Clear notebook outputs before uploading
- Don't include large CSV/audio files
- Use `.gitignore` to exclude data files if needed

### Notebooks not rendering on GitHub
- Make sure they're valid `.ipynb` files (JSON format)
- Try re-exporting from Jupyter
- GitHub sometimes takes a few minutes to render

### Want to hide API keys?
- Never commit API keys!
- Use `.env` files (already in `.gitignore`)
- Use environment variables

---

Good luck! 🎉
