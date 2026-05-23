# 🏠 Vancouver Housing Market — Machine Learning Predictive Modeling

**A Data Science Project Analyzing Housing Price Drivers in Vancouver, BC**

![Python](https://img.shields.io/badge/Python-3.13-blue) ![Scikit-Learn](https://img.shields.io/badge/scikit--learn-1.8-green) ![Pandas](https://img.shields.io/badge/pandas-3.0-orange)

---

## 📊 Project Overview

This project applies **machine learning** to understand what drives housing prices in Vancouver. Using data from 3,860+ properties across 22 neighborhoods, we built predictive models to identify key price factors and discovered natural market segments.

**Key Question:** *What factors determine Vancouver housing prices?*

---

## 🎯 Results at a Glance

### 🏆 Best Model: Random Forest
- **Testing R²:** 87.05% (explains 87% of price variation)
- **MAE:** $297,602 (average prediction error)
- **RMSE:** $529,809
- **Improvement over Linear Regression:** +9.67% accuracy, $135K lower error

### 🔑 Top 3 Price Drivers
1. **Square Footage** — 77.6% importance (dominant!)
2. **Longitude** — 11.2% importance (east-west location)
3. **Latitude** — 3.7% importance (north-south location)

### 💰 Price by Neighborhood

| Neighborhood | Avg Price | Status |
|---|---|---|
| 🏰 Shaughnessy | $5,690,714 | Luxury |
| 🌊 West Point Grey | $4,001,537 | Premium |
| 🌳 Dunbar-Southlands | $3,894,745 | Premium |
| 🎯 Kerrisdale | $3,525,057 | Premium |
| 🏢 Downtown | $1,367,827 | Condo Market |
| 🏘️ Strathcona | $1,058,906 | Budget |

> **5x+ price variation across neighborhoods — location is a key price driver!**

### 🤖 Market Segments (K-Means)
- **Budget** — Affordable East Vancouver
- **Mid-Range** — Standard market properties
- **Premium** — High-end West side homes
- **Luxury** — Ultra-premium $5M+ properties

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
│   ├── 04_geographic_analysis.ipynb   # Interactive heatmap & geographic analysis
│   └── 05_clustering.ipynb            # K-Means market segmentation
│
├── data/
│   ├── raw/                           # Raw datasets (not tracked by Git)
│   │   ├── canada_housing/
│   │   └── local-area-boundary.geojson
│   └── processed/
│       ├── housing_data_cleaned.csv
│       ├── housing_data_ml_ready.csv
│       ├── vancouver_with_neighborhoods.csv
│       └── neighborhood_analysis.csv
│
├── outputs/
│   ├── figures/
│   │   ├── price_distribution.png
│   │   ├── correlation_heatmap.png
│   │   ├── price_log_transform.png
│   │   ├── 03_lr_predictions.png
│   │   ├── 03_rf_predictions.png
│   │   ├── 03_model_comparison.png
│   │   ├── 03_feature_importance.png
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

> **Notebook order:** `01_eda` → `02_cleaning` → `02b_spatial_join` → `03_modeling` → `04_geographic_analysis` → `05_clustering`

---

## 🏆 Model Comparison

### Linear Regression (Baseline)

| Metric | Value |
|---|---|
| Training R² | 0.7839 |
| Testing R² | 0.7738 (77.4%) |
| MAE | $433,070 |
| RMSE | $700,136 |
| CV R² (5-fold) | 0.7275 ± 0.0343 |

### Random Forest (Winner) 🏆

| Metric | Value |
|---|---|
| Training R² | 0.9815 |
| Testing R² | **0.8705 (87.1%)** |
| MAE | **$297,602** |
| RMSE | **$529,809** |
| CV R² (5-fold) | **0.8316 ± 0.0398** |

> **Winner: Random Forest** — explains 87% of price variation with an average error of $297,602.

---

## 📊 Notebooks Overview

**01_eda.ipynb** — Exploratory Data Analysis
- Price distribution, correlation heatmap, missing values analysis

**02_cleaning.ipynb** — Data Cleaning
- Price outlier removal, feature selection, log-transform

**02b_spatial_join.ipynb** — Geographic Mapping
- GeoJSON spatial join → 22 neighborhoods, one-hot encoding

**03_modeling.ipynb** — Predictive Modeling
- Linear Regression vs Random Forest, 5-fold CV, feature importance

**04_geographic_analysis.ipynb** — Geographic Visualization
- Interactive folium heatmap, neighborhood price rankings

**05_clustering.ipynb** — Market Segmentation
- K-Means (K=4), 4 market tiers, interactive cluster maps

---

## 🔑 Key Insights

**For Buyers:**
- Square footage is the #1 price driver (77.6%)
- Budget properties cluster in East Vancouver (Strathcona, Killarney)
- Luxury properties concentrated on the West side

**For Sellers:**
- West-side location commands 5x+ premium
- Shaughnessy avg $5.69M — highest tier
- Downtown median $988K — condo-dominated market

**For Real Estate Professionals:**
- Random Forest achieves 87% pricing accuracy
- 4-tier market segmentation for client matching
- Neighborhood comparison tools available

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
01_eda → 02_cleaning → 02b_spatial_join → 03_modeling → 04_geographic_analysis → 05_clustering
```

---

## 📦 Technologies

- **Python 3.13** — Core language
- **pandas, numpy** — Data processing
- **scikit-learn** — Machine learning (LR, RF, KMeans)
- **geopandas, shapely** — Geospatial analysis
- **matplotlib, seaborn** — Static visualization
- **folium** — Interactive maps
- **Jupyter Notebook** — Development environment

---

## 📊 Data

| Source | Records | Features |
|---|---|---|
| Kaggle Canada Housing | ~44,896 total | 23 |
| Vancouver GeoJSON | 22 neighborhoods | Boundaries |
| **Final ML Dataset** | **3,542** | **34** |

---

## 👥 Team

| Name | Role |
|---|---|
| **Majda** | EDA · Data Cleaning · Spatial Join · Geographic Visualization |
| **Geny** | Machine Learning Models · Clustering · Feature Importance |

---

## 🌿 Git Workflow

```
main
 └── development
      ├── feature/eda-spatial-analysis     (Majda)
      └── feature/modeling-lr-rf           (Geny)
```

---

## 📅 Timeline

| Week | Focus | Status |
|---|---|---|
| Week 2 | EDA, cleaning, spatial join, models | ✅ Done |
| Week 3 | Heatmap, clustering, model comparison | ✅ Done |
| Week 4 | Final report & presentation | 🎤 Due May 30 |

---

## 🚀 Future Work

- Hyperparameter tuning (GridSearchCV)
- XGBoost & advanced ensemble models
- Real-time pricing API integration
- Web deployment dashboard
- Time-series price trend analysis

---

## 📄 Data Sources

- [Kaggle — Canada Housing Dataset](https://www.kaggle.com/datasets/yuliiabulana/canada-housing)
- [City of Vancouver Open Data — Local Area Boundary](https://opendata.vancouver.ca/explore/dataset/local-area-boundary/)

---

*DS302 Final Project · CICCC Data Science Program · 2025–2026*
