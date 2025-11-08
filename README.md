# 🎓 Predicting Student GPA using Multiple Linear Regression

## 1️⃣ Introduction
This project applies **Multiple Linear Regression (MLR)** to predict students’ **GPA** based on two key academic factors:
- **SAT Score** — a measure of standardized test performance.
- **Class Attendance** — a binary indicator of regular participation (1 = attended, 0 = not attended).

The goal is to understand how these predictors jointly influence GPA and build a model that can estimate student performance with reasonable accuracy.

---

## 2️⃣ Methodology

### 🧾 Data Description
The dataset (`Student_data.csv`) contains information about students’ SAT scores, attendance status, and GPAs.

| Feature        | Type        | Description |
|----------------|--------------|-------------|
| `SAT`          | Numeric     | Standardized test score |
| `Attendance`   | Categorical | Yes = 1 (attended), No = 0 (did not attend) |
| `GPA`          | Numeric     | Student grade point average |

### 🔧 Data Preprocessing
- **Encoding**: Converted the categorical “Attendance” variable into numerical format using binary mapping (`Yes → 1`, `No → 0`).
- **Missing Values**: Checked for and confirmed there were no missing data.
- **Feature Scaling**: Not required since MLR handles scale automatically here.

### 📊 Exploratory Data Analysis
Correlation analysis revealed:
- **SAT vs GPA:** Strong positive correlation (**r = 0.637**)
- **Attendance vs GPA:** Moderate-to-strong positive correlation (**r = 0.540**)

This suggests that both SAT and Attendance are valuable predictors of GPA.

---

## 3️⃣ Findings
### 🧮 Model Building

We trained a Multiple Linear Regression model using:

Predictors (X): SAT, Attendance

Target (y): GPA

Train-Test Split: 80% training, 20% testing.

### 📈 Model Equation

The trained model can be expressed as:

GPA = 0.0017 × SAT + 0.222 × Attendance + 0.643

Each 1-point increase in SAT raises GPA by ~0.0017 points.

Attending class regularly adds ~0.22 GPA points on average.
### ✅ Model Evaluation

| Metric   | Train Set | Test Set | Interpretation                             |
| -------- | --------- | -------- | ------------------------------------------ |
| **MAE**  | 0.131     | 0.134    | Average prediction error ≈ 0.13 GPA points |
| **MSE**  | 0.029     | 0.029    | Small squared error — good accuracy        |
| **RMSE** | 0.171     | 0.171    | Typical deviation ≈ 0.17 GPA points        |
| **R²**   | 0.553     | 0.576    | Explains ~55–58% of GPA variation          |

---


## 4️⃣ Interpretation & Insights
### 🔍 Key Insights

SAT scores are the strongest predictor of GPA.

Attendance still has a meaningful impact: students who attend classes regularly achieve higher GPAs, even when SAT scores are similar.

The model captures 55–58% of GPA variance — reasonable for a simple academic dataset.

### 🎯 Predictions Example
| Student | SAT  | Attendance | Predicted GPA |
| ------- | ---- | ---------- | ------------- |
| James   | 1550 | 1          | 3.09          |
| Daniel  | 1670 | 1          | 3.24          |
| Grace   | 1700 | 0          | 3.05          |
- Even with a higher SAT, Grace’s lower attendance slightly reduced her predicted GPA — showing that consistency matters!

---

## 5️⃣ Recommendations

Encourage consistent attendance to boost academic performance.

Use SAT + Attendance analytics to identify at-risk students early.

Introduce academic mentoring programs for students with low attendance but strong SAT potential.

---
## 6️⃣ Conclusion

This analysis demonstrates that a simple Multiple Linear Regression model can effectively predict GPA using SAT scores and attendance rates.
While SAT reflects academic aptitude, consistent class attendance significantly enhances learning outcomes — reinforcing the importance of engagement alongside intelligence.

---
## 📘 Technologies Used
- Python (Pandas, NumPy, Matplotlib, Seaborn)
- Scikit-learn
- Jupyter Notebook

---
- Author: David Adepegba
- Project: Week 2 of Machine Learning Journey — Multiple Linear Regression
- Dataset: <a href='https://github.com/adepegba1/Dataset/blob/main/Student_data.csv'>Student_Data.csv</a>
