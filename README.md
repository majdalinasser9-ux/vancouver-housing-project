# 🏠 Vancouver Housing Price Analysis
### Machine Learning Project — Predictive Modelling Report

> Can machine learning predict Vancouver housing prices? This project analyzes real housing market data across Vancouver's 22 neighborhoods to identify key price drivers and build predictive models.

---

## 👥 Team

| Name | Role |
|------|------|
| Majda | EDA · Data Cleaning · Spatial Join · Geographic Visualization |
| Geny | Machine Learning Models · Feature Importance · Model Comparison |

---

## 📌 Project Overview

We build and compare two machine learning models — **Linear Regression** and **Random Forest** — to predict residential housing prices in Vancouver, BC. We evaluate each model's performance, identify the most important price predictors, and present findings with geographic visualizations.

**Core Questions:**
- Which neighborhoods are the most and least expensive — and why?
- What property features most strongly affect price?
- Can we accurately predict housing prices using ML?

---

## 🎯 Project Goals

- **Exploratory Analysis** — Understand price distributions, correlations, and outliers
- **Data Cleaning** — Remove outliers and prepare a clean dataset for modeling
- **Spatial Join** — Map each property to one of Vancouver's 22 neighborhoods using GeoJSON
- **Predictive Modeling** — Build and compare Linear Regression and Random Forest
- **Feature Importance** — Identify which factors most strongly influence price
- **Geographic Analysis** — Create an interactive price heatmap across Vancouver
- **Actionable Insights** — Data-driven recommendations for buyers, sellers, and investors

---

## 📁 Project Structure

```
vancouver-housing-project/
│
├── notebooks/
│   ├── 01_eda.ipynb                   # Exploratory Data Analysis
│   ├── 02_cleaning.ipynb              # Data cleaning & feature engineering
│   ├── 02b_spatial_join.ipynb         # Spatial join — adds neighbourhood column
│   ├── 03_modeling.ipynb              # Linear Regression & Random Forest models
│   └── 04_geo_visualization.ipynb     # Interactive heatmap & geographic analysis
│
├── data/
│   ├── raw/
│   │   ├── canada_housing/            # Kaggle Canada housing dataset
│   │   └── local-area-boundary.geojson
│   └── processed/
│       ├── vancouver_housing_cleaned.csv
│       ├── housing_data_ml_ready.csv          # Input to modeling notebook
│       ├── vancouver_with_neighborhoods.csv
│       └── neighborhood_analysis.csv
│
├── outputs/
│   ├── figures/
│   │   ├── price_distribution.png
│   │   ├── correlation_heatmap.png
│   │   ├── rf_feature_importance.png
│   │   ├── 04_neighborhoods_by_price.png
│   │   └── vancouver_price_heatmap.html
│   └── models/
│       ├── linear_regression_model.pkl
│       └── random_forest_model.pkl
│
├── src/
│   └── __init__.py
├── requirements.txt
└── README.md
```

> **Notebook order matters:** `01_eda` → `02_cleaning` → `02b_spatial_join` → `03_modeling` → `04_geo_visualization`

---

## 📊 Key Findings

### Neighborhood Price Analysis

| Neighborhood | Avg Price | Median Price | Properties |
|---|---|---|---|
| 🏰 Shaughnessy | $8,171,901 | $7,185,000 | 74 |
| 🌊 West Point Grey | $6,109,759 | $4,050,000 | 87 |
| 🎯 Kerrisdale | $5,712,916 | $4,180,000 | 109 |
| 🏢 Downtown | $1,518,970 | $989,400 | 790 |
| 🏘️ Strathcona | $1,026,237 | $823,500 | 34 |

> **Key Insight:** There is an **8x price variation** across Vancouver neighborhoods. Location is the single strongest driver of housing price.

### Dataset Summary
- **3,860** Vancouver properties loaded and filtered
- **3,375** properties after cleaning
- **22** neighborhoods mapped via spatial join
- Features include: bedrooms, bathrooms, square footage, latitude/longitude, neighborhood (one-hot encoded)

---

## 🤖 ML Models

| Attribute | Linear Regression | Random Forest |
|---|---|---|
| Type | Parametric / Linear | Ensemble / Non-linear |
| Interpretability | High — coefficients | Medium — feature importance |
| Training speed | Fast | Slower (100 trees) |
| Risk of overfit | Low | Moderate (managed by `max_depth=20`) |

### Model Results

| Metric | Linear Regression | Random Forest | Winner |
|---|---|---|---|
| Testing R² | — | — | — |
| MAE ($) | — | — | — |
| RMSE ($) | — | — | — |
| CV R² (5-fold) | — | — | — |

> To be filled in after Notebook 03 is complete.

---

## 🗺️ Geographic Analysis

- Interactive price heatmap: `outputs/figures/vancouver_price_heatmap.html`
- Neighborhood price bar chart: `outputs/figures/04_neighborhoods_by_price.png`
- Spatial join using official Vancouver GeoJSON boundary data

---

## 🚀 Getting Started

### 1. Clone the repository
```bash
git clone https://github.com/majdalinasser9-ux/vancouver-housing-project.git
cd vancouver-housing-project
```

### 2. Set up virtual environment
```bash
python -m venv .venv
source .venv/bin/activate      # Mac/Linux
# or .venv\Scripts\activate    # Windows
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

### 4. Download datasets
- **Kaggle Canada Housing** → [kaggle.com/datasets/yuliiabulana/canada-housing](https://www.kaggle.com/datasets/yuliiabulana/canada-housing) → save to `data/raw/canada_housing/`
- **Vancouver GeoJSON** → [opendata.vancouver.ca](https://opendata.vancouver.ca/explore/dataset/local-area-boundary/) → save to `data/raw/local-area-boundary.geojson`

### 5. Run notebooks in order
```
01_eda → 02_cleaning → 02b_spatial_join → 03_modeling → 04_geo_visualization
```

> Use `housing_data_ml_ready.csv` as input to `03_modeling.ipynb` — this file includes the spatial join and one-hot encoded neighborhood columns.

---

## 📦 Dependencies

```
pandas · numpy · scikit-learn · matplotlib · seaborn
geopandas    # spatial join
folium       # interactive heatmap
shapely · jupyter
```

---

## 🌿 Git Workflow

```
main
 └── development
      ├── feature/eda-spatial-analysis     (Majda)
      └── feature/modeling-lr-rf           (Geny)
```

- Work on your feature branch
- Clear notebook outputs before committing (`Cell → All Output → Clear`)
- Open a Pull Request → `development` when done
- Teammate reviews before merge

---

## 📅 Timeline

| Week | Focus | Deliverables |
|---|---|---|
| Week 2 | EDA, cleaning, spatial join, models | All notebooks, CSVs, PR |
| Week 3 | Heatmap, model comparison, presentation draft | Heatmap HTML, slide deck |
| Week 4 | Polish, rehearsal, final presentation | Final slides |
| **May 30** | **Final presentation** | 🎓 |

---

## 📄 Data Sources

- [Kaggle — Canada Housing Dataset](https://www.kaggle.com/datasets/yuliiabulana/canada-housing)
- [City of Vancouver Open Data — Local Area Boundary](https://opendata.vancouver.ca/explore/dataset/local-area-boundary/)

---

*DS301 Final Project · CICCC Data Science Program · 2025–2026*
