# 🏠 Vancouver Housing Market — Machine Learning Predictive Modeling

**A Data Science Project Analyzing Housing Price Drivers in Vancouver, BC**

![Python](https://img.shields.io/badge/Python-3.13-blue) ![Scikit-Learn](https://img.shields.io/badge/scikit--learn-1.8-green) ![Pandas](https://img.shields.io/badge/pandas-3.0-orange)

---

## 📊 PROJECT OVERVIEW

This project applies **machine learning** to understand what drives housing prices in Vancouver. Using data from 3,860+ properties across 22 neighborhoods, we built predictive models to identify key price factors and discovered natural market segments.

**Key Question:** *What factors determine Vancouver housing prices?*

---

## 🎯 RESULTS AT A GLANCE

### 🏆 Best Model: Random Forest
- **Testing R²:** 87.05% (explains 87% of price variation)
- **MAE:** $297,602 (average prediction error)
- **RMSE:** $529,809
- **Accuracy:** Significantly outperforms Linear Regression baseline by 9.67%

### 🔑 Top 3 Price Drivers
1. **Square Footage** — 77.6% importance (dominant!)
2. **Longitude** — 11.2% importance (east-west location)
3. **Latitude** — 3.7% importance (north-south location)

### 💰 Price by Neighborhood
| Neighborhood | Avg Price | Status |
|---|---|---|
| 🏰 Shaughnessy | $8.17M | Luxury |
| 🌊 West Point Grey | $6.11M | Premium |
| 🎯 Kerrisdale | $5.71M | Premium |
| 🏘️ Strathcona | $1.03M | Budget |
| **8x difference!** | — | **Location matters** |

### 🤖 Market Segments (K-Means)
- **Budget:** Affordable East Vancouver
- **Mid-Range:** Standard market properties
- **Premium:** High-end West side homes
- **Luxury:** Ultra-premium $5M+ properties

---

## 📁 PROJECT STRUCTURE
vancouver-housing-project/
├── notebooks/
│   ├── 01_eda.ipynb                 # EDA & visualizations
│   ├── 02_cleaning.ipynb            # Data preprocessing
│   ├── 02b_spatial_join.ipynb       # Map to neighborhoods
│   ├── 03_modeling.ipynb            # LR & Random Forest models
│   └── 05_clustering.ipynb          # K-Means segmentation
├── data/
│   ├── raw/
│   │   ├── canada_housing/          # Kaggle dataset
│   │   └── local-area-boundary.geojson
│   └── processed/
│       ├── vancouver_housing_cleaned.csv
│       └── vancouver_with_neighborhoods.csv
├── outputs/
│   ├── figures/
│   │   ├── 03_rf_predictions.png
│   │   ├── 03_feature_importance.png
│   │   ├── 04_neighborhoods_by_price.png
│   │   ├── 05_vancouver_clusters_map.html
│   │   └── vancouver_price_heatmap.html
│   └── models/
│       ├── linear_regression_model.pkl
│       └── random_forest_model.pkl
├── requirements.txt
└── README.md
---

## 📊 NOTEBOOKS OVERVIEW

### **01_eda.ipynb** — Exploratory Data Analysis
- Price distribution analysis ($289K - $49.8M)
- Correlation heatmap (Square footage: 0.83)
- Missing values assessment & cleaning

### **02b_spatial_join.ipynb** — Geographic Mapping
- GeoJSON spatial join: properties → neighborhoods
- 22 neighborhoods identified
- Neighborhood price analysis (8x variation)

### **03_modeling.ipynb** — Predictive Modeling ✅
- Linear Regression: R² = 0.7738
- **Random Forest: R² = 0.8705** 🏆
- Feature importance rankings
- Model comparison & evaluation

### **05_clustering.ipynb** — Market Segmentation
- K-Means clustering (K=4)
- 4 market tiers identified
- Interactive neighborhood maps
- Cluster characteristic analysis

---

## 🏆 MODEL COMPARISON

### Linear Regression (Baseline)
| Metric | Value |
|--------|-------|
| Testing R² | 0.7738 (77.4%) |
| MAE | $433,070 |
| RMSE | $700,136 |
| CV R² | 0.7275 ± 0.0343 |

### Random Forest (WINNER) 🏆
| Metric | Value |
|--------|-------|
| Testing R² | **0.8705 (87.1%)** |
| MAE | **$297,602** |
| RMSE | **$529,809** |
| CV R² | **0.8316 ± 0.0398** |

**Improvement:** 9.67% higher accuracy, $135K lower error

---

## 🔑 KEY INSIGHTS

### For Buyers:
✅ Square footage is #1 price driver (77.6%)  
✅ Location matters less than size (combined 14.9%)  
✅ Budget properties cluster in East Vancouver  
✅ Luxury properties concentrated on West side  

### For Sellers:
✅ Maximize square footage for value  
✅ West-side location commands 5-8x premium  
✅ Shaughnessy avg $8.17M (luxury tier)  
✅ Downtown median $1.52M (condo market)  

### For Real Estate Professionals:
✅ 87% accurate pricing predictions  
✅ Use Random Forest model for valuations  
✅ 4-tier market segmentation for client matching  
✅ Neighborhood comparison tools available  

---

## 🛠️ SETUP INSTRUCTIONS

### Prerequisites
- Python 3.10+
- pip

### Installation
```bash
git clone https://github.com/majdalinasser9-ux/vancouver-housing-project.git
cd vancouver-housing-project

python -m venv .venv
source .venv/bin/activate  # Mac/Linux
# or .venv\Scripts\activate (Windows)

pip install -r requirements.txt
```

### Run Notebooks
```bash
jupyter notebook notebooks/01_eda.ipynb
```

---

## 📊 DATA

| Source | Records | Features |
|--------|---------|----------|
| Kaggle Canada Housing | 15,000 | 24 |
| Vancouver GeoJSON | 22 neighborhoods | Boundaries |
| **Final Dataset** | **3,375** | **16** |

**Data Quality:**
- ✅ 3,860 Vancouver properties extracted
- ✅ 485 rows removed (missing values)
- ✅ All features cleaned & validated

---

## 📦 TECHNOLOGIES

- **Python 3.13** — Core language
- **pandas, numpy** — Data processing
- **scikit-learn** — Machine learning (LR, RF, KMeans)
- **geopandas, shapely** — Geospatial analysis
- **matplotlib, seaborn** — Static visualization
- **folium** — Interactive maps
- **Jupyter Notebook** — Development environment

---

## 👥 TEAM

- **[Your Name]** — EDA, Spatial Analysis, Geographic Visualization
- **Geny** — Data Cleaning, Predictive Modeling, Clustering

---

## 📅 PROJECT TIMELINE

- **Week 1:** ✅ Setup & EDA
- **Week 2:** ✅ Spatial Join & Geographic Analysis
- **Week 3:** ✅ Modeling & Clustering
- **Week 4:** 📄 Final Report & 🎤 Presentation (Due May 30)

---

## 📈 QUICK STATS
Neighborhoods: 22
Properties: 3,875
Price Range: $289,900 - $49,800,000
Median Price: $1,539,800
Model Accuracy: 87.05%
Top Feature: Square Footage (77.6%)

---

## 🚀 FUTURE WORK

- [ ] Hyperparameter tuning
- [ ] XGBoost & advanced models
- [ ] Real-time pricing API
- [ ] Web deployment
- [ ] Time-series price trends

---

## 📞 CONTACT

**GitHub Issues:** [Report bugs or ask questions](https://github.com/majdalinasser9-ux/vancouver-housing-project/issues)

---

**Built with ❤️ for Vancouver real estate insights**  
**Last Updated:** May 2026
