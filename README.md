# 🌱 Crop Recommender System (Soil + Climate → Best Crop)

🧭 **Goal:** Recommend the most suitable crop given **soil nutrients + environmental conditions** using a multi-class classification model.

📌 **Inputs (features):** `N, P, K, temperature, humidity, ph, rainfall`  
🎯 **Output (target):** `label` (crop type)

---

## 📊 Findings

✅ **Dataset**
- 2,200 samples across **22 crops** (balanced: **100 samples per crop**)
- Data loaded from `Crop_recommendation.csv`

🔎 **EDA insights**
- **Phosphorus (P)** and **Potassium (K)** show a strong positive relationship (**corr ≈ 0.74**), suggesting overlapping soil patterns for some crops
- Distribution checks showed:
  - Temperature centered around ~25°C (roughly bell-shaped)
  - Rainfall skewed toward lower values (right-skew)
  - Humidity skewed toward higher values (left-skew)

🧪 **Statistical testing (ANOVA)**
- Environmental variables differ meaningfully across crops:
  - Temperature: **F ≈ 102.19**, **p ≈ 4.0e-305**
  - Rainfall: **F ≈ 605.53**, **p = 0.0**
  - Humidity: **F ≈ 3103.71**, **p = 0.0**
- Conclusion: temperature/humidity/rainfall are **highly informative** for separating crop classes

🧠 **Modeling**
- Standardized features with **StandardScaler**
- Trained a **Logistic Regression** multi-class classifier as the baseline (interpretable coefficients per crop class)

📈 **Model performance (test set)**
- Accuracy: **0.96** (support = 440)
- Macro avg: **Precision 0.96 | Recall 0.97 | F1 0.96**
- Confusion matrix indicated the model correctly classified most crop types with only limited confusion among a few classes

---

## 👤 Author

Imanuel Annoh
