# 🏠 Vancouver Housing Price Analysis

> A machine learning project exploring the key factors that influence property prices across Vancouver's 22 neighborhoods.

---

## 👥 Team

| Name | Role | GitHub |
|------|------|--------|
| Majda | EDA, Spatial Analysis, Geographic Visualization | [@majdalinasser9-ux](https://github.com/majdalinasser9-ux) |
| Geny | Machine Learning Models (LR & Random Forest) | — |

---

## 📌 Project Overview

This project analyzes real housing market data in Vancouver to identify the key factors influencing property prices and develop predictive models. By combining exploratory data analysis with machine learning and geographic analysis, we generate meaningful insights into Vancouver's competitive housing market.

**Core Questions:**
- Which neighborhoods are the most and least expensive — and why?
- What property features (size, bedrooms, bathrooms) most affect price?
- Can we accurately predict housing prices using machine learning?

---

## 🎯 Project Goals

- **Exploratory Analysis** — Understand data distributions, correlations, and relationships between property features and prices
- **Predictive Modeling** — Build and compare Linear Regression and Random Forest models
- **Feature Importance** — Identify which property factors most strongly influence housing prices
- **Geographic Analysis** — Analyze price variations across Vancouver's 22 neighborhoods using boundary data
- **Actionable Insights** — Provide data-driven recommendations for buyers, sellers, and investors

---

## 📁 Project Structure

```
vancouver-housing-project/
│
├── notebooks/
│   ├── 01_eda.ipynb                  # Exploratory Data Analysis
│   ├── 02b_spatial_join.ipynb        # Spatial join with neighborhood boundaries
│   ├── 03_modeling.ipynb             # Linear Regression & Random Forest models
│   └── 04_geographic_analysis.ipynb  # Interactive maps & neighborhood visualizations
│
├── data/
│   ├── raw/
│   │   ├── canada_housing/           # Kaggle Canada housing dataset
│   │   └── local-area-boundary.geojson  # Vancouver neighborhood boundaries
│   └── processed/
│       ├── vancouver_housing_cleaned.csv
│       ├── vancouver_with_neighborhoods.csv
│       └── neighborhood_analysis.csv
│
├── outputs/
│   ├── figures/                      # Charts, heatmaps, visualizations
│   └── models/                       # Saved ML models (.pkl)
│
├── src/
│   └── __init__.py
│
├── requirements.txt
└── README.md
```

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

> **Key Insight:** Location explains an 8x price variation across Vancouver — neighborhood is the single strongest driver of housing price.

### Dataset Summary
- **3,860** total Vancouver properties loaded
- **3,375** properties after cleaning
- **22** neighborhoods mapped via spatial join
- **16** features used for modeling

---

## 🤖 ML Models

Two models were built and compared:

| Model | Description |
|---|---|
| **Linear Regression** | Baseline model — fast, interpretable, shows feature coefficients |
| **Random Forest** | Ensemble of 100 decision trees — higher accuracy, feature importance scores |

Both models use 5-Fold Cross-Validation and are evaluated on R², MAE, and RMSE.

---

## 🗺️ Geographic Analysis

- Interactive price heatmap of Vancouver (`outputs/figures/vancouver_price_heatmap.html`)
- Neighborhood bar chart — top 15 most expensive areas
- Spatial join using GeoJSON boundary data to assign each property to its neighborhood

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
source .venv/bin/activate  # Mac/Linux
# or .venv\Scripts\activate  # Windows
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

### 4. Run notebooks in order
```
01_eda.ipynb → 02b_spatial_join.ipynb → 03_modeling.ipynb → 04_geographic_analysis.ipynb
```

---

## 📦 Dependencies

```
pandas
numpy
scikit-learn
matplotlib
seaborn
geopandas
folium
shapely
jupyter
```

---

## 📅 Timeline

| Week | Focus |
|---|---|
| Week 2 | EDA, data cleaning, spatial join, baseline models |
| Week 3 | Model comparison, geographic heatmap, feature importance |
| Week 4 | Final report, presentation, polish — due May 30 |

---

## 📄 Data Sources

- [Kaggle — Canada Housing Dataset](https://www.kaggle.com/datasets/yuliiabulana/canada-housing)
- [City of Vancouver Open Data — Local Area Boundary](https://opendata.vancouver.ca/explore/dataset/local-area-boundary/)

---

*DS301 Final Project — CICCC Data Science Program*
