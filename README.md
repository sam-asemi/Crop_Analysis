# 🌱 Sowing Success: Using Machine Learning to Help Farmers Choose the Right Crops

Modern agriculture often relies on expensive and time-consuming soil testing to assess field conditions. This project explores how **machine learning** can help farmers **identify the most suitable crop** to plant based on essential soil metrics—saving both time and money.

---

## 🧠 Objective

To evaluate which soil metrics are most predictive of optimal crop selection using a classification model, and to identify the single most informative feature that can help farmers make better planting decisions.

---

## 📊 Dataset Overview

**File:** `soil_measures.csv`

Each row represents soil measurements from a specific field, with the best-matching crop labeled in the `crop` column.

**Features:**
- `N`: Nitrogen content in the soil
- `P`: Phosphorous content in the soil
- `K`: Potassium content in the soil
- `pH`: Acidity/alkalinity of the soil
- `crop`: Optimal crop (target variable)

---

## 🔬 Methodology

- Loaded and cleaned the data with `pandas`
- Target: `crop` (multiclass classification)
- Trained separate **logistic regression** models using each feature independently
- Evaluated models using **F1 score** (weighted) to account for class imbalance

---

## 🧪 Results

| Feature | F1 Score |
|---------|----------|
| N       | 0.0915   |
| P       | 0.1476   |
| **K**   | **0.2390** |
| pH      | 0.0458   |

✅ **Potassium (K)** proved to be the most predictive single feature for determining the optimal crop choice.

---

## ⚠️ Notes

- The `LogisticRegression` model showed convergence warnings. This is a known issue when using a single feature on multiclass problems. You can resolve it by:
  - Increasing `max_iter`
  - Scaling features using `StandardScaler`
- The `multi_class='multinomial'` parameter is now default in `scikit-learn` 1.7+

---

## 🛠️ Tools Used

- Python
- pandas
- scikit-learn
- F1 Score (weighted) from `sklearn.metrics`

---

## 🌾 Key Takeaway

This project demonstrates how even simple machine learning models can provide actionable insights in agriculture. With just one soil feature—**potassium**—farmers can make more informed decisions on what crop to plant, especially when facing budget constraints on full soil analysis.
