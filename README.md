# 🏨 Hotel Booking Cancellation Prediction (Logistic Regression)

This project predicts whether a hotel booking will be cancelled using a **Logistic Regression model** trained on real-world hotel booking data.

The goal is to help hotels reduce revenue loss by identifying high-risk bookings in advance.

---

## 📌 Problem Statement

Hotel cancellations lead to:
- Revenue loss
- Poor resource allocation
- Operational inefficiency

👉 Objective:
> Predict whether a booking will be cancelled (1) or not (0)

---

## 📊 Dataset Overview

The dataset contains real booking records from city and resort hotels, including customer behavior, booking details, and pricing information.

**Dataset**: https://www.sciencedirect.com/science/article/pii/S2352340918315191?utm_source=chatgpt.com#ec0006

### 🎯 Target Variable:
- `IsCanceled`
  - `0` → Not Cancelled  
  - `1` → Cancelled  

---

## 🧹 Data Preprocessing

### 1. Data Cleaning
- Removed duplicate records
- Handled missing values in:
  - Country
  - Children
  - Agent
- Removed leakage features:
  - `ReservationStatus`
  - `ReservationStatusDate`

---

### 2. Feature Engineering
Created meaningful features like:

- `TotalGuests = Adults + Children + Babies`
- `TotalNights = StaysInWeekendNights + StaysInWeekNights`
---

### 3. Encoding
- One-Hot Encoding applied to:
  - MarketSegment
  - Meal
  - DepositType
  - CustomerType
  - DistributionChannel
  - ReservedRoomType
  - ArrivalDateMonth

- Binary features kept as 0/1 (no encoding needed)

---

### 4. Feature Scaling
- StandardScaler applied to numerical features like:
  - LeadTime
  - ADR
  - TotalGuests
  - TotalNights
  - BookingChanges

---

## 🤖 Model Used

- Logistic Regression

### Why Logistic Regression?
- Interpretable model
- Works well for binary classification
- Provides probability outputs for risk scoring
- Industry-standard baseline model

---

## 🧪 Train-Test Split

- 80% training data  
- 20% testing data  
- `random_state = 42` (for reproducibility)

---

## 📈 Model Evaluation Results

- **Accuracy:** 0.788  
- **Precision:** 0.541  
- **Recall:** 0.814  
- **F1 Score:** 0.650  
- **ROC-AUC Score:** 0.80  

---

## 🧠 Interpretation of Results

### 📊 Accuracy (78.8%)
The model correctly predicts around **79% of bookings**, but accuracy alone is not sufficient for evaluation.

---

### 🎯 Precision (54.1%)
Only 54% of predicted cancellations are actually correct.

👉 This indicates some false alarms (false positives), meaning the model sometimes over-predicts cancellations.

---

### 🔍 Recall (81.4%) ⭐
The model correctly identifies **81% of all actual cancellations**.

👉 This is the most important metric for this problem because:
- Missing a cancellation leads to revenue loss
- High recall ensures most risky bookings are captured

---

### ⚖️ F1 Score (65.0%)
Balances precision and recall, showing a reasonable trade-off between:
- Catching cancellations
- Avoiding false alarms

---

### 📈 ROC-AUC Score (0.80) ⭐
The model has good ability to distinguish between cancelled and non-cancelled bookings.

👉 Interpretation:
- 0.5 → Random model  
- 0.8 → Good predictive power  
- 1.0 → Perfect model  

✔ This score confirms the model is reliable for ranking cancellation risk.

---

## 🏨 Business Impact

This model helps hotels:

- Identify high-risk bookings early
- Reduce revenue loss from cancellations
- Improve overbooking strategy
- Optimize pricing and deposit policies

👉 The model works best as a **risk prediction system**, not a fully automated decision tool.

---

## 📊 Key Insights

- Longer lead times → higher cancellation probability
- Non-refundable deposits reduce cancellations
- Repeat guests are less likely to cancel
- Certain market segments have higher cancellation risk
- More special requests → lower chance of cancellation

---

## 🛠 Tech Stack

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib / Seaborn

---

## 🚀 Future Improvements

- Hyperparameter tuning (C, penalty, solver)
- Try advanced models (Random Forest, XGBoost)
- Threshold optimization for better recall/precision trade-off
- Deploy using Streamlit or Flask
- Add real-time prediction API

---

## 📁 Project Structure

hotel-booking-cancellation/
│
├── data/
├── notebooks/
├── README.md
└── model/


---

## 👨‍💻 Author

- Data Science Project – Logistic Regression Machine Learning Project  
- Focus: Classification, Feature Engineering, and Model Interpretation  

---

## ⭐ If you like this project

Give it a ⭐ on GitHub and feel free to explore or improve it!