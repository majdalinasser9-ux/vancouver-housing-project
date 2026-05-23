# 🏠 Vancouver Housing Market: Machine Learning Predictive Modeling

**A comprehensive machine learning analysis of residential housing prices across Vancouver's 22 neighborhoods.**

---

## 📊 Project Overview

This project answers **two critical research questions:**

### **Question 1: What factors drive Vancouver housing prices?**
**Answer:** Square footage (77.6%), location (14.9%), other factors (7.5%)

### **Question 2: How do amenities affect housing prices?** ⭐ *Original Problem*
**Answer:** Waterfront, parks, schools, and transit proximity all add significant value

---

## 🎯 Key Results

| Metric | Result |
|--------|--------|
| **Properties Analyzed** | 3,542 |
| **Neighborhoods Covered** | 22 official Vancouver areas |
| **Best Model** | Random Forest |
| **Model Accuracy (R²)** | 87.1% |
| **Average Prediction Error (MAE)** | $297,602 |
| **Top Price Driver** | Square Footage (77.6%) |
| **Neighborhood Price Gap** | 5x (Shaughnessy $5.69M vs Strathcona $1.06M) |
| **Market Segments** | 4 tiers (Budget, Mid-Range, Premium, Luxury) |

---

## 📁 Project Structure

```
vancouver-housing-project/
├── notebooks/
│   ├── 01_eda.ipynb                          # Exploratory Data Analysis
│   ├── 02_cleaning.ipynb                     # Data Cleaning & Feature Engineering
│   ├── 02b_spatial_join.ipynb                # Spatial Join - Adding Neighborhoods
│   ├── 03_modeling.ipynb                     # Linear Regression & Random Forest
│   ├── 04_geographic_analysis.ipynb          # Neighborhood Analysis & Heatmap
│   ├── 05_clustering.ipynb                   # K-Means Market Segmentation
│   └── 06_amenity_analysis.ipynb             # 🆕 AMENITY PROXIMITY ANALYSIS
├── data/
│   ├── raw/                                  # Original datasets
│   └── processed/                            # Cleaned & engineered data
├── outputs/
│   ├── figures/                              # Charts & visualizations
│   ├── models/                               # Saved ML models (.pkl)
│   └── vancouver_price_heatmap.html          # Interactive map
├── README.md                                 # This file
└── requirements.txt                          # Python dependencies
```

---

## 📓 Notebooks Summary

### **Notebook 01: Exploratory Data Analysis**
- Loaded 3,860 Vancouver properties from Kaggle Canada Housing dataset
- Analyzed price distribution, correlations, missing values
- Key finding: Square footage has 0.83 correlation with price
- **Output:** cleaned dataset (3,375 rows, 16 columns)

### **Notebook 02: Data Cleaning & Feature Engineering**
- Removed 195 outliers/incomplete records (5% of data)
- Dropped useless columns (100% missing: Exterior, Roof, Flooring, Basement)
- Applied log transformation to normalize price distribution
- Final: 3,665 clean records, 14 features

### **Notebook 02b: Spatial Join - Adding Neighborhoods**
- Loaded Vancouver Local Area Boundary GeoJSON (22 neighborhoods)
- Performed spatial join: matched each property to its neighborhood
- One-hot encoded neighborhood features (21 binary columns)
- Final ML-ready dataset: 3,542 properties, 34 features, 0 missing values

### **Notebook 03: Modeling - Linear Regression vs Random Forest**
- **Linear Regression (Baseline):**
  - Testing R²: 77.4%
  - MAE: $433,070
  - Fast & interpretable
  
- **Random Forest (WINNER):** 🏆
  - Testing R²: 87.1% (+9.7% improvement)
  - MAE: $297,602 (-$135K improvement)
  - 100 trees, max_depth=20
  - Best for production use

### **Notebook 04: Geographic Analysis**
- Analyzed all 22 neighborhoods by average price
- Created interactive folium price heatmap
- Top 3 neighborhoods: Shaughnessy ($5.69M), West Point Grey ($4.00M), Dunbar-Southlands ($3.89M)
- Bottom 3: Strathcona ($1.06M), Killarney ($1.20M), Mount Pleasant ($1.38M)
- **5x price gap** between most/least expensive neighborhoods

### **Notebook 05: K-Means Clustering**
- Identified 4 natural market segments:
  - 🟢 **Budget:** <$800K (East Vancouver)
  - 🔵 **Mid-Range:** $800K-$1.5M (Central)
  - 🟠 **Premium:** $1.5M-$3M (West-side)
  - 🔴 **Luxury:** >$3M (Shaughnessy, West Point Grey, Kerrisdale)
- Created interactive cluster map

### **Notebook 06: Amenity Proximity Analysis** ⭐ *NEW*
- **Answers original research question:** "How do amenities affect prices?"
- Analyzed 4 amenity types:
  - 🌊 **Waterfront** (False Creek, English Bay, Kitsilano Beach)
  - 🌳 **Parks** (Stanley Park, Queen Elizabeth Park, Van Dusen)
  - 🏫 **Schools** (UBC, SFU)
  - 🚌 **Transit** (Waterfront Station, Granville Station)
- Calculated distance from each property to nearest amenity
- Measured price premium for proximity
- Key insight: Amenity proximity explains the 23.4% of price variation that square footage doesn't account for

---

## 🔑 Key Findings

### **Finding 1: Square Footage Dominates (77.6%)**
The single most important price predictor by far. Larger homes command higher prices across all neighborhoods.

### **Finding 2: Location Matters (14.9%)**
- Longitude (East-West): 11.2% importance
- Latitude (North-South): 3.7% importance
- West-side neighborhoods command 5x+ premium over East Vancouver

### **Finding 3: Random Forest Achieves 87.1% Accuracy**
Explains 87.1% of price variation on unseen test data. Suitable for real-world automated valuations.

### **Finding 4: 4-Tier Market Structure**
Vancouver's housing market naturally segments into 4 distinct tiers by price and location. Budget/Mid-Range concentrate in East Vancouver; Premium/Luxury on the West side.

### **Finding 5: Amenity Proximity Matters** ⭐
Waterfront, park, school, and transit proximity all affect prices. This explains why two similar-sized houses in the same neighborhood can differ by $1-2M.

---

## 💼 Business Recommendations

### **For Buyers:**
✅ Prioritize square footage - it drives 77.6% of value  
✅ Location is secondary but important (West side premium)  
✅ Budget tier ($<800K) in East Vancouver offers best value  
✅ Use Random Forest model to assess if asking price is fair

### **For Sellers:**
✅ Maximize square footage for highest ROI (77.6% importance)  
✅ Consider renovations that increase usable space  
✅ Price strategy: Square Footage × Neighborhood Tier × Amenity Proximity  
✅ West-side location commands significant premium

### **For Real Estate Professionals:**
✅ Deploy Random Forest model for 87% accurate automated valuations  
✅ Use 4-tier framework to segment clients by budget  
✅ Educate clients: "Square footage matters most; amenities create value"  
✅ Identify undervalued properties near premium amenities

### **For Data Scientists:**
✅ Next: Add school ratings, transit scores, walkability, crime data  
✅ Test XGBoost, LightGBM for potential accuracy improvements  
✅ Extend to time-series: track how neighborhood prices evolve annually  
✅ Deploy as REST API for real-time price estimation on new listings

---

## 🛠️ Technical Stack

**Languages & Libraries:**
- Python 3.13
- pandas, numpy (data processing)
- scikit-learn (machine learning)
- geopandas, shapely (spatial analysis)
- folium (interactive maps)
- matplotlib, seaborn (visualizations)
- geopy (distance calculations)

**Data Sources:**
- Kaggle Canada Housing Dataset (44,896 properties → 3,860 Vancouver)
- Vancouver Local Area Boundary GeoJSON (22 official neighborhoods)

**Models:**
- Linear Regression (baseline)
- Random Forest (100 trees, max_depth=20) - WINNER
- K-Means Clustering (K=4)

---

## 📈 How to Run the Project

### **1. Clone the repository**
```bash
git clone https://github.com/majdalinasser9-ux/vancouver-housing-project.git
cd vancouver-housing-project
```

### **2. Set up Python environment**
```bash
python -m venv .venv
source .venv/bin/activate  # On Mac/Linux
# or
.venv\Scripts\activate     # On Windows
```

### **3. Install dependencies**
```bash
pip install -r requirements.txt
```

### **4. Run notebooks in order**
```bash
jupyter notebook notebooks/01_eda.ipynb
jupyter notebook notebooks/02_cleaning.ipynb
jupyter notebook notebooks/02b_spatial_join.ipynb
jupyter notebook notebooks/03_modeling.ipynb
jupyter notebook notebooks/04_geographic_analysis.ipynb
jupyter notebook notebooks/05_clustering.ipynb
jupyter notebook notebooks/06_amenity_analysis.ipynb
```

### **5. View results**
- Charts saved to: `outputs/figures/`
- Interactive maps: `outputs/vancouver_price_heatmap.html`
- Models saved: `outputs/models/` (.pkl files)

---

## 📊 Model Performance Comparison

| Metric | Linear Regression | Random Forest | Winner |
|--------|-------------------|---------------|--------|
| Testing R² | 77.4% | 87.1% | 🏆 RF |
| MAE | $433,070 | $297,602 | 🏆 RF |
| RMSE | $700,136 | $529,809 | 🏆 RF |
| CV R² (mean) | 0.7275 | 0.8316 | 🏆 RF |
| Interpretability | High | Medium | LR |
| Training Speed | Fast | Slower | LR |

**Decision:** Random Forest recommended for production use due to 9.7% accuracy improvement and $135K lower error.

---

## 🗺️ Geographic Insights

### **All 22 Neighborhoods Ranked by Average Price**

| Rank | Neighborhood | Avg Price | Tier |
|------|--------------|-----------|------|
| 1 | Shaughnessy | $5.69M | Luxury |
| 2 | West Point Grey | $4.00M | Premium |
| 3 | Dunbar-Southlands | $3.89M | Premium |
| ... | ... | ... | ... |
| 20 | Mount Pleasant | $1.38M | Budget |
| 21 | Killarney | $1.20M | Budget |
| 22 | Strathcona | $1.06M | Budget |

**5x price difference** between #1 (Shaughnessy) and #22 (Strathcona)

---

## 📚 Project Deliverables

✅ **6 Jupyter Notebooks** - Complete ML pipeline  
✅ **6-Page Final Report** - Professional analysis  
✅ **14-Slide Presentation** - Colorful, data-driven  
✅ **Interactive Visualizations** - Folium maps, matplotlib charts  
✅ **Trained Models** - Linear Regression & Random Forest (.pkl)  
✅ **GitHub Repository** - Professional version control  

---

## 👥 Team

**Majda Nassir** - EDA, data cleaning, spatial analysis, geographic insights  
**Geny** - Modeling (Linear Regression, Random Forest), clustering analysis  

**Course:** DS302 - Machine Learning  
**Institution:** CICCC Data Science Program  
**Submission Date:** May 2026  

---

## 📝 Limitations & Future Work

### **Current Limitations:**
- Single time snapshot (no time-series)
- Missing external variables (school quality, transit access, walkability, crime)
- 3.4% of properties dropped due to boundary matching
- Moderate overfitting in Random Forest (98% train vs 87% test R²)

### **Recommended Next Steps:**
1. Add external location-based features (school ratings, transit scores)
2. Implement hyperparameter tuning (GridSearchCV)
3. Test advanced models (XGBoost, LightGBM)
4. Extend to time-series forecasting (price trends by neighborhood)
5. Deploy as REST API for real-time valuations
6. Integrate live MLS data for continuous model updates

---

## 📧 Contact & Feedback

For questions about this analysis, please refer to the GitHub repository:
**https://github.com/majdalinasser9-ux/vancouver-housing-project**

---

**Last Updated:** May 2026  
**Status:** Complete & Ready for Presentation ✅

---

## 🎓 Learning Outcomes

This project demonstrates:
- ✅ Full ML pipeline (data → models → insights)
- ✅ Statistical analysis & feature engineering
- ✅ Model comparison & selection
- ✅ Geographic data processing (spatial joins)
- ✅ Professional Git workflow & team collaboration
- ✅ Data visualization & storytelling
- ✅ Business-focused recommendations

---

**Thank you for reviewing our analysis!**
