# 🚕 Multi-Class Surge Pricing Prediction for Taxi Mobility

## 📖 Project Overview
This project aims to predict **surge pricing type** (multi-class classification) for a taxi company operating in India.  
By leveraging historical trip and customer data, the model identifies key drivers of surge pricing and provides **actionable business insights** to support **vehicle allocation and pricing optimization**.

---

## 🎯 Business Objective
The taxi company has been operating for less than one year and has recorded multiple surge pricing types.  
The goals of this project are to:

- Predict surge pricing type (Low, Medium, High)
- Identify features that most influence surge pricing
- Provide recommendations to optimize fleet allocation and pricing strategy

---

## ❓ Business Questions
1. What is the distribution of surge pricing types?
2. Which features most influence surge pricing classification?
3. Based on model insights, what operational recommendations can be given?

---

## 📊 Dataset Information
- **Source:** Kaggle – *Trip Pricing with Taxi Mobility Analytics*
- **Rows:** 131,662
- **Columns:** 14 (original), expanded to 26 after encoding
- **Link:** https://www.kaggle.com/datasets/arashnic/taxi-pricing-with-mobility-analytics

---

## 🧹 Data Preprocessing
### Missing Value Handling
| Feature | Strategy |
|------|---------|
| Type_of_Cab | Mode |
| Customer_Since_Months | -1 |
| Life_Style_Index | Median |
| Confidence_Life_Style_Index | Mode |
| Var1 | Median |

### Feature Engineering
- One-Hot Encoding for categorical variables
- Feature Scaling for numerical variables
- Train/Test Split: **80% / 20%**
- Class imbalance handled using **SMOTE**

---

## 🔍 Exploratory Data Analysis (EDA)
Key observations:
- **Surge Type 2** is dominant (43%)
- **Surge Type 3** has the highest average trip distance (~49 km)
- **Surge Type 3** also shows the highest cancellation rate in the last month

---

## 🔗 Multicollinearity Check
- **VIF Score:** All features < 2 (no serious multicollinearity)
- **Correlation Heatmap:** No strong linear dependency detected

This ensures model stability and reliable feature interpretation.

---

## 🤖 Modeling Approach
### Models Evaluated
- K-Nearest Neighbors (kNN)
- Logistic Regression
- Random Forest

Each model was tested **with and without hyperparameter tuning**.

### Evaluation Metrics
- **Accuracy**
- **Macro F1-Score** (used to fairly evaluate all classes)

---

## 🏆 Best Model Performance
| Model | Test Accuracy | Test Macro-F1 |
|----|----|----|
| Random Forest | 0.66 | 0.67 |

**Random Forest** showed the most stable and balanced performance across all classes after tuning.

---

## 🔎 Feature Importance (SHAP Analysis)
Top drivers of surge pricing:
1. **Type_of_Cab (A, D, B)** – strongest influence
2. **Cancellation_Last_1Month**
3. **Confidence_Life_Style_Index & Life_Style_Index**
4. **Trip_Distance & Customer_Rating**
5. **Destination_Type, Var1, Var2**
6. **Customer_Since_Months & Gender** (least impact)

---

## 💡 Business Insights & Recommendations
### 1️⃣ Cab Type as Primary Driver
Certain cab types are consistently associated with higher surge pricing.

**Recommendation:**
- Increase or reallocate Cab A, B, and D fleets in high-demand zones and peak time windows to reduce extreme surge.

### 2️⃣ Customer Cancellation Behavior
Higher cancellation frequency correlates with surge-prone conditions.

**Recommendation:**
- Implement cancellation penalties or loyalty incentives to reduce last-minute cancellations and improve supply stability.

---

## 🧾 Conclusion
- Random Forest achieved **66% accuracy** and **67% Macro-F1**, performing fairly across all surge classes.
- Cab type and customer behavior are the strongest drivers of surge pricing.
- The model can be used as a **decision-support tool** for fleet allocation and pricing optimization.

---

## 👤 Author
**Antonius Wisnumurti Sulistyanto**  
📧 Email: antoniuswisnumurti@gmail.com  
🔗 LinkedIn: https://www.linkedin.com/in/antonius-wisnumurti-sulistyanto/

---

## ⚠️ Notes
This project is intended for analytical and educational purposes and reflects patterns observed in historical data.
