# NBA Defensive Player of the Year (DPOY) Prediction Model

This project builds a predictive model to forecast the 2025-26 NBA Defensive Player of the Year winner using historical data from 2014-15 to 2023-24 seasons.

## 📁 Project Structure
```
dpoy_prediction/
├── dpoy_analysis.ipynb          # Main analysis notebook (RUN THIS)
├── data/
│   ├── raw/                     # Raw data from NBA API
│   │   ├── player_stats_historical.csv
│   │   ├── player_stats_current.csv
│   │   ├── team_stats_historical.csv
│   │   ├── team_stats_current.csv
│   │   └── dpoy_votes.csv
│   └── processed/               # Processed/engineered features
│       ├── training_data_full.csv
│       ├── training_data.csv
│       ├── test_data.csv
│       └── current_season_data.csv
├── outputs/
│   ├── predictions.csv          # FINAL DELIVERABLE
│   └── visualizations/          # Charts for slides
│       ├── 1_feature_importance.png
│       ├── 2_top_10_predictions.png
│       ├── 3_model_performance.png
│       └── 4_probability_distribution.png
├── requirements.txt             # Python dependencies
└── README.md                    # This file
```

## 🚀 Quick Start

### 1. Install Dependencies
```bash
pip install -r requirements.txt
```

### 2. Run the Analysis

Open and run `dpoy_analysis.ipynb` in Jupyter Notebook:
```bash
jupyter notebook dpoy_analysis.ipynb
```

**OR** if using JupyterLab:
```bash
jupyter lab dpoy_analysis.ipynb
```

### 3. Run All Cells

- Click **Cell → Run All** in Jupyter
- The notebook will execute end-to-end:
  - Section 1: Data Collection (if raw data exists, loads it; otherwise collects from NBA API)
  - Section 2: Data Cleaning & Feature Engineering
  - Section 3: Model Training & Validation
  - Generates `outputs/predictions.csv` and visualizations

**Expected runtime:** ~5-10 minutes (depending on API rate limits)

## 📊 Output Files

After running the notebook, you'll find:

1. **`outputs/predictions.csv`** - 2025-26 DPOY predictions
   - Format: `player_name, probability`
   - Sorted by probability (descending)

2. **`outputs/visualizations/`** - 4 charts for presentation:
   - Feature importance
   - Top 10 predictions
   - Model performance
   - Probability distribution

## 🔧 Model Details

- **Model Type:** Linear Regression
- **Target Variable:** DPOY vote share (0-1)
- **Training Data:** 2014-15 to 2022-23 seasons (2,002 players)
- **Test Data:** 2023-24 season (222 players)
- **Key Features:**
  - Defense impact (stocks × team quality)
  - Availability score (games × minutes)
  - Team defensive rank
  - Per-36 minute stats (steals, blocks)

## 📝 Notes

- **Data Source:** NBA API (`nba_api` package) and Basketball Reference
- **2025-26 Predictions:** Based on early season data with estimated team defensive rankings
- **Reproducibility:** All data collection and processing is automated in the notebook

