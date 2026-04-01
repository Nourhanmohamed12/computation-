Housing Price Analysis & Prediction Pipeline
Comprehensive Exploratory Data Analysis (EDA) and Support Vector Regression (SVR) pipeline for predicting housing prices using the King County Housing dataset.

Features

Complete EDA Pipeline: Data loading, cleaning, visualization
Outlier Detection & Removal: Z-score based filtering
Dimensionality Reduction: PCA with 90% variance retention
Three SVR Models: RBF, Linear, Polynomial kernels
Model Comparison: RMSE-based performance evaluation
Rich Visualizations: Histograms, scatter plots, box plots, correlation heatmap, scree plot

📊 Dataset
King County Housing Dataset (21,613 records × 21 features)

Key Features: price, bedrooms, bathrooms, sqft_living, sqft_lot, grade, lat, long
Target: price (continuous)

🚀 Quick Start
Prerequisites

pip install pandas numpy matplotlib seaborn scikit-learn

python housing_analysis.py

🛠️ Pipeline Overview

1. Data Loading → 2. EDA → 3. Outlier Removal → 4. PCA → 5. SVR Modeling → 6. Evaluation
1. Data Quality Checks

✅ No missing values (21,613/21,613)
✅ No duplicates (0)
✅ Date parsing completed

2. Exploratory Visualizations
Line Histograms + KDE: 17 numerical features
Scatter Plots: Price vs key features (sqft_living, bedrooms, etc.)
Box Plots: Outlier identification across all features
Correlation Heatmap: High correlations (>0.8) identified

4. Outlier Removal

Method: Z-score (threshold=1)
Removed: ~96% outliers
Remaining: 887 clean records

4. Dimensionality Reduction

Original: 18 features
PCA Components: 11 (90% variance retained)
PC1 Variance: 31.05%

5. SVR Model Comparison
Kernel RMSE Status
RBF 2.349 🥇 Best
Polynomial 2.365 🥈
Linear 2.429 🥉

📈 Key Insights

Copy code
🔥 Strongest Price Correlations:
- sqft_living (r ≈ 0.7+)
- grade
- sqft_above

⚠️  Outliers: Heavy right skew in price, sqft_lot
📍 Geographic: lat/long show clear Seattle patterns

🔍 Code Structure

# Core Components
├── data_loading.py      # CSV → DataFrame + date parsing
├── eda_visualizations.py # Histograms, scatters, boxplots
├── outlier_removal.py   # Z-score filtering
├── pca_reduction.py     # 90% variance PCA
├── svr_models.py        # RBF/Linear/Poly + RMSE
└── main_pipeline.py     # Orchestration

🎨 Sample Visualizations

1. Line Histogram + KDE (17 features)
2. Price vs Key Features (4-panel scatter)
3. Outlier Boxplots (9 panels × 3)
4. Correlation Heatmap (coolwarm)
5. PCA Scree Plot
6. SVR Prediction Plot (RBF best)
7. 
📁 Requirements

pandas>=1.5.0
numpy>=1.21.0
matplotlib>=3.5.0
seaborn>=0.11.0
scikit-learn>=1.0.0

# PCA variance target  
PCA_THRESHOLD = 0.90  # 95% for more components

# SVR hyperparameters
SVR_C = 100
SVR_EPSILON = 0.1

🧪 Example Output

Original shape: (21613, 18)
PCA Components: 11 (90.0% variance)
RMSE RBF: 2.3487 ← Best Model
RMSE Linear: 2.4290
RMSE Polynomial: 2.3654

🤝 Contributing
Fork repository
Add new visualizations/models
Update outlier detection
Submit PR with test results

👩‍💻 Author

Nourhan Mohammed
Computer Science Student | Data Enthusiast
