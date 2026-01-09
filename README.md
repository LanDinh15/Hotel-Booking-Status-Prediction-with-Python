# Hotel Booking Status Prediction 🏨📊

## Overview
This project predicts whether a hotel booking will be **canceled or confirmed** using supervised machine learning techniques.  
Multiple models and feature selection methods were evaluated to identify the most accurate and stable solution.

The final model achieved **~90.2% accuracy** with strong cross-validation performance.

---

## Dataset
- **Source:** Hotel reservation dataset (36,275 records)
- **Target Variable:** `booking_status`
  - `0` = Not Canceled
  - `1` = Canceled
- **Features:** Guest demographics, booking behavior, pricing, arrival details, and booking channel

**Class Distribution:**
- Not Canceled: ~67%
- Canceled: ~33% (imbalanced dataset)

---

## Project Workflow

### 1. Data Preprocessing
- Removed irrelevant identifier (`Booking_ID`)
- Checked for missing values and duplicates
- Separated numerical and categorical features
- Encoded target variable

---

### 2. Exploratory Data Analysis (EDA)
- Visualized class imbalance
- Analyzed numeric and categorical feature distributions
- Correlation analysis with booking status

**Key Insights:**
- Longer `lead_time` increases cancellation likelihood
- Fewer `special_requests` correlates with higher cancellation rates
- Online bookings cancel more frequently than offline

---

### 3. Feature Engineering
- **Numerical features:** StandardScaler
- **Categorical features:** OneHotEncoder
- Implemented using `ColumnTransformer` for pipeline consistency

---

### 4. Feature Selection Techniques
The following methods were evaluated:
- Tree-based selection (Random Forest importance)
- SelectKBest (Mutual Information)
- L1 Regularization (Logistic Regression)

---

### 5. Models Evaluated
Seven supervised models were tested:
- Logistic Regression  
- Naive Bayes  
- Decision Tree  
- Random Forest  
- Support Vector Machine (SVM)  
- K-Nearest Neighbors (KNN)  
- XGBoost  

Each model was combined with multiple feature selection techniques.

---

## Results Summary

### Best Model
**Random Forest + L1-based Feature Selection**

| Metric | Score |
|------|------|
| Accuracy | **0.9016** |
| F1-score | **0.84** |
| Cross-validation Accuracy | **0.9023** |

---

### Classification Report
- Strong performance on both classes
- Slightly lower recall for canceled bookings due to class imbalance

---

### Top Important Features
1. `lead_time`
2. `avg_price_per_room`
3. `no_of_special_requests`
4. `arrival_date`
5. `arrival_month`
6. Booking channel (Offline vs Online)

---

## Technologies Used
- Python
- Pandas, NumPy
- Scikit-learn
- XGBoost
- Matplotlib, Seaborn

---

## Output Files
- `hotel_project_results.xlsx`
  - Cleaned Data
  - Encoded Data
  - Model Accuracy Comparison

---

## Key Takeaways
- Tree-based models outperform linear models on this dataset
- Feature selection improves both accuracy and interpretability
- Guest booking behavior is a strong predictor of cancellations

---

## Future Improvements
- Handle class imbalance using SMOTE or class weighting
- Add ROC-AUC and precision-recall analysis
- Deploy model using Streamlit or Flask

---

## Author
**Lan Dinh**  
Data Analytics / Machine Learning Project
