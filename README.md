# 🏠 Ames Housing Price Prediction & Investment Analysis

## 📌 Table of Contents
1. [Project Overview](#-project-overview)
2. [Business Intelligence Highlights](#-business-intelligence-highlights)
   - [Valuation Insights](#-valuation-insights)
   - [Renovation ROI Strategy](#-renovation-roi-strategy)
   - [Neighborhood Tier Analysis](#-neighborhood-tier-analysis)
3. [Data Foundations & Feature Engineering](#-data-foundations--feature-engineering)
   - [Missing & Outlier Treatment](#-missing--outlier-treatment)
   - [Feature Construction](#-feature-construction)
4. [Model Architecture & Evaluation](#-model-architecture--evaluation)
   - [Regression Models Used](#-regression-models-used)
   - [Model Accuracy](#-model-accuracy)
   - [Top Predictive Drivers](#-top-predictive-drivers)
5. [Strategic Recommendations](#-strategic-recommendations)
6. [References & Methodology](#-references--methodology)
7. [Contact](#-contact)

---

## 🔍 Project Overview

This project presents a comprehensive valuation and investment analysis of the Ames Housing market using advanced data science techniques. It integrates preprocessing, engineered features, regression modeling, and business logic to extract high-ROI opportunities.

**Goals Achieved:**
- Quantified valuation gaps across 1,460 residential properties  
- Identified $12.7M in undervalued equity  
- Modeled renovation strategies with ROI ranging from 63–116%  
- Tiered neighborhoods by price appreciation for acquisition targeting

---

## 📊 Business Intelligence Highlights

### 🎯 Valuation Insights

- **Mean Absolute Error:** 12.6% on temporally split test data  
- **Premium Bias:** 8.2% underprediction in Tier 2 homes  
- **Garage Capacity:** Each car space adds ~$14,491  
- **Remodel Decay:** Home value drops ~$1,951/year post-renovation

### 💰 Renovation ROI Strategy

| Improvement      | Avg. Cost | Value Add | ROI  | Applicable Tier |
|------------------|-----------|-----------|------|------------------|
| Quality 5→7      | $30,000   | $48,500   | 63%  | Tier 1 → 3        |
| Bathroom Add     | $22,000   | $38,700   | 76%  | Tier 2            |
| Open Concept     | $18,500   | $27,900   | 51%  | Tier 3            |

> 📌 Guideline: Avoid over-improvement—do not exceed the ceiling quality score of the target neighborhood tier.

### 📈 Neighborhood Tier Analysis

| Tier | Median Price | Growth Rate | Key Traits                          |
|------|--------------|-------------|-------------------------------------|
| 1    | $131,500     | 3.1%/year   | 1960–1980 homes, needs updates      |
| 2    | $285,000     | 6.5%/year   | Post-2000 builds, premium finishes  |
| 3    | $190,000     | 4.2%/year   | 1990s remodeled colonials           |

> 💡 Investment Tip: Focus acquisitions on Tier 1 homes near Tier 3 zones for highest equity uplift.

---

## 🧪 Data Foundations & Feature Engineering

### 🧼 Missing & Outlier Treatment

- **Sparsity Cleansing:** Dropped features with >90% nulls (e.g., `PoolQC`, `Alley`)  
- **Domain Imputation:** `FireplaceQu → "None"` for homes without fireplaces  
- **Precision Imputation:** `LotFrontage →` neighborhood median + missing indicator  
- **Multivariate Outlier Handling:** DBSCAN and LOF used to flag 42 anomalous homes  
- **Extreme Adjustments:** 3+ kitchens capped to 2, oversized lots log-transformed

### 🧠 Feature Construction

- **Interaction Terms:**
  - `QualXTotalSF (r=0.856)` – Key value predictor  
  - `BathXBedroom` – Renovation scale indicator  

- **Temporal Features:**
  - `RemodAge`, `IsRemodeled`, `HouseAge`  

- **Luxury Flags:**
  - `HasPool`, `HasFireplace`, `IsCornerLot`  

- **Normalization:** Log/Square-root transforms applied to skewed numeric features

---

## 🔍 Model Architecture & Evaluation

### 🧮 Regression Models Used

- **Linear Regression:** Baseline model with fast training and interpretability  
- **Polynomial Regression (2nd Degree):** Captures non-linear effects in quality × size relationships  
- **Temporal Validation Framework:** Evaluated stability using pre-2010 training and 2010 test split

### 📊 Model Accuracy

| Model Type          | MAE   | RMSE     | Use Case                   |
|---------------------|-------|----------|----------------------------|
| Linear Regression   | 11.2% | $38,269  | Rapid benchmark valuation  |
| Polynomial Regression | 7.3% | $34,343  | Premium asset targeting    |
| Temporal Validation | 12.6% | $30,079  | Historical trend forecasting |

### 🔑 Top Predictive Drivers

| Driver                   | Effect                                 |
|--------------------------|----------------------------------------|
| Quality × Size Interaction | +$28.4k per quality × 1,000 sqft      |
| Garage Capacity           | +$14,491 per car space                 |
| Remodel Recency           | −$1,951/year depreciation              |

---

## 📌 Strategic Recommendations

### 🏡 For Investors

- Acquire Tier 1 homes near Tier 3 boundaries  
- Prioritize 1950–1980 constructions with cosmetic renovation potential  
- Budget $15k per upgrade quality level  
- Flip Tier 1 assets in 2–3 years; hold Tier 2 assets for 5+ years

### 🏗️ For Developers

- Build 2,100–2,600 sqft units in Tier 3 with quality level 7–8 finishes  
- Convert ranch-style homes into open-concept layouts  
- Avoid corner lots and pre-1940 homes due to lower absorption and higher maintenance

---

## 📚 References & Methodology

- **Dataset:** Ames Housing Dataset (Kaggle)  
- **Validation Approach:** Temporal split — pre-2010 train, 2010 test  
- **Modeling Techniques:** Linear and Polynomial regression with feature interaction analysis  
- **Outlier Strategy:** DBSCAN + Local Outlier Factor (LOF)

---

## 📬 Contact

- ✉️ **Email:** [i.sajeela.noor@gmail.com](mailto:i.sajeela.noor@gmail.com)  
- 💼 **LinkedIn:** [Sajeela Noor](https://www.linkedin.com/in/sajeela-noor-82b510256)
