# Climatic-Driven Groundwater Level Prediction using Machine Learning

## 📌 Project Overview
Groundwater is a vital global resource, but monitoring it dynamically can be challenging. This project develops an end-to-end machine learning regression pipeline to predict monthly **Groundwater Levels (GWL)** based on key hydro-climatic variables. By benchmarking multiple AI frameworks, this study evaluates how effectively surface climate variations map to deeper aquifer behavior.

## 📊 Dataset & Features
The dataset integrates local daily groundwater readings with monthly spatial climate data from TerraClimate spanning several decades. The independent variables (features) used are:
* **Pr (Precipitation):** Input moisture into the hydrological system.
* **Sm (Soil Moisture):** Water content held in the soil layer.
* **ETa (Actual Evapotranspiration):** Water returned to the atmosphere by soil and plants.
* **ETo (Reference Evapotranspiration):** Atmospheric demand for moisture.
* **Ta_Max / Ta_Min:** Monthly maximum and minimum ambient air temperatures.

**Target Variable:** Monthly average Groundwater Level (GWL) in meters.

## ⚙️ Methodology & Pipeline Steps
1. **Data Temporal Resampling:** Transformed raw daily groundwater records into uniform monthly averages to align with macro-climate datasets.
2. **Feature Engineering & Alignment:** Executed a strict temporal inner-join on datetime indices to ensure zero data misalignment.
3. **Exploratory Data Analysis (EDA):** Evaluated individual feature distributions via histograms and analyzed linear/non-linear dependencies using bivariate scatter plots.
4. **Robust Validation Stack:** Implemented a **3-Fold Cross-Validation (K-Fold)** structure to ensure generalizability and prevent evaluation bias.
5. **Algorithmic Benchmarking:** Compared four distinct mathematical paradigms:
   * Ensembles: **Gradient Boosting** and **Random Forest** Regressors.
   * Geometric Distance-Margins: **Support Vector Regressor (SVR)** wrapped in a feature-scaling pipeline.
   * Baseline Splitting: **Decision Tree Regressor**.

## 📈 Final Performance Leaderboard
The models were evaluated using the Coefficient of Determination ($R^2$) and Root Mean Squared Error (RMSE):

| Rank | Model | $R^2$ Score | RMSE (meters) |
| :---: | :--- | :---: | :---: |
| **1** | **Gradient Boosting Regressor** | **0.3983** | **3.6495 m** |
| **2** | **Random Forest Regressor** | 0.3796 | 3.7068 m |
| **3** | **Support Vector Regressor (SVR)** | 0.3726 | 3.7227 m |
| **4** | **Decision Tree Regressor** | 0.2886 | 3.9649 m |

### 🔍 Core Insights
* **Ensemble Superiority:** Sequential tree architectures (Gradient Boosting) outperformed structural margin bounds (SVR) and single-tree frameworks, showcasing their resilience against overfitting on tabular environmental indicators.
* **Hydrological Lag Context:** The moderate baseline $R^2$ (~0.40) highlights a fundamental domain trait: groundwater systems experience delayed infiltration responses to precipitation, paving the way for future sequential feature-lag modeling.

### Run
Open "https://github.com/PinarKavousi/groundwater-level-prediction/blob/main/Ground%20Water%20Prediction.ipynb" in Jupyter Notebook and run all cells
