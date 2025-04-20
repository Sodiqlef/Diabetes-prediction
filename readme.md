# Diabetes Prediction using Logistic Regression

This project uses the **Pima Indians Diabetes Dataset** to predict whether a patient is likely to have diabetes based on medical attributes. A logistic regression model was trained and evaluated to perform the binary classification.

---

## 📂 Dataset Description

The dataset consists of 768 entries and 9 columns:

| Column         | Description                                                       |
| -------------- | ----------------------------------------------------------------- |
| `num_preg`     | Number of times the patient has been pregnant                     |
| `glucose_conc` | Plasma glucose concentration (from oral glucose tolerance test)   |
| `diastolic_bp` | Diastolic blood pressure (mm Hg)                                  |
| `thickness`    | Skin fold thickness (mm) — an estimate of body fat                |
| `insulin`      | 2-Hour serum insulin (mu U/ml)                                    |
| `bmi`          | Body Mass Index = weight (kg) / height² (m²)                      |
| `diab_pred`    | Diabetes pedigree function — genetic risk based on family history |
| `age`          | Age of the person (in years)                                      |
| `diabetes`     | Target variable: 1 = diabetic, 0 = non-diabetic                   |

---

## 🧹 Data Cleaning & Preprocessing

- **Zero-value handling**: Replaced invalid `0` entries (e.g., in `glucose_conc`, `bmi`, `insulin`) with the **mean** of their respective columns.
- **Multicollinearity check**: Correlation heatmap used to identify relationships between features.
- **EDA**: Visualized feature distributions using box plots to explore differences in diabetes status.

---

## 📊 Exploratory Data Analysis

- **Age and pregnancy count** showed noticeable differences between diabetic and non-diabetic patients.
- The target variable (`diabetes`) was **slightly imbalanced**, with ~65% of the samples being non-diabetic.

---

## 🤖 Model Training

- **Algorithm**: Logistic Regression (`sklearn`)
- **Train/Test Split**: 80/20
- **Performance**:
  - Baseline Accuracy: **65.1%**
  - Training Accuracy: **76.9%**
  - Test Accuracy: **76.6%**

---

## 🔍 Feature Importance (Model Coefficients)

| Feature        | Coefficient |
| -------------- | ----------- |
| `num_preg`     | 0.0673      |
| `glucose_conc` | 0.0381      |
| `diastolic_bp` | -0.0147     |
| `thickness`    | 0.0016      |
| `insulin`      | -0.0021     |
| `bmi`          | 0.1079      |
| `diab_pred`    | 0.5767      |
| `age`          | 0.0346      |

> The **diabetes pedigree function** (`diab_pred`) and **BMI** are strong predictors in the logistic regression model.

---

## 🛠 Tools & Libraries

- Python
- Pandas, NumPy
- Seaborn, Matplotlib
- Scikit-learn

---

## 📌 Conclusion

- Logistic regression provides a solid baseline model for predicting diabetes.
- `diab_pred`, `bmi`, and `glucose_conc` had the most impact on the likelihood of having diabetes.
- Further improvements can include scaling, hyperparameter tuning, and testing more complex models like Random Forest or XGBoost.

---