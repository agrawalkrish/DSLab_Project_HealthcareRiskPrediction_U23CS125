# ❤️ Heart Disease Risk Prediction using Machine Learning  
A complete machine learning pipeline to predict the likelihood of heart disease using patient clinical attributes and advanced classification models.

---

## 📌 Overview  
Heart disease is one of the leading causes of death globally. Early detection can significantly improve patient outcomes.

This project builds an end-to-end predictive system that:

- Predicts heart disease risk using patient health data  
- Compares linear and ensemble machine learning models  
- Uses ROC-AUC for robust evaluation  
- Identifies key medical features influencing predictions  

---

## 🎯 Objectives  
- Predict presence of heart disease with high accuracy  
- Compare performance of multiple ML models  
- Interpret important health indicators  
- Build a scalable and reproducible ML pipeline  

---

## 📊 Dataset  
**Source:** UCI Machine Learning Repository (Heart Disease Dataset)

- Total Samples: **303**  
- Features: **13 input features + 1 target**  

### Key Features:
- `age` → Patient age  
- `sex` → Gender  
- `cp` → Chest pain type  
- `trestbps` → Resting blood pressure  
- `chol` → Cholesterol level  
- `thalach` → Maximum heart rate achieved  
- `exang` → Exercise-induced angina  
- `oldpeak` → ST depression  
- `ca` → Number of major vessels  
- `thal` → Thalassemia type  

### Target:
- `0` → No heart disease  
- `1` → Presence of heart disease  

⚠️ Note: Missing values found in `ca` and `thal` were handled during preprocessing.

---

## ⚙️ Tech Stack  
**Language:** Python  

**Libraries:**
- NumPy, Pandas  
- Scikit-learn  
- Matplotlib, Seaborn  

---

## 🔄 Workflow Pipeline  
**Data Loading → EDA → Preprocessing → Model Training → Evaluation → Feature Importance → Model Refinement**

---

## 🧹 Data Preprocessing  

✅ Missing value imputation  
- Numerical → Median  
- Categorical → Most frequent  

✅ Feature scaling  
- StandardScaler applied to numerical features  

✅ Encoding  
- OneHotEncoding for categorical variables  

✅ Train-Test Split  
- 80% Training / 20% Testing (Stratified)  

---

## 📈 Exploratory Data Analysis (EDA)  

Key insights:

- Balanced dataset (healthy vs disease cases)  
- Strong correlations observed between:
  - Chest pain type (`cp`)  
  - Maximum heart rate (`thalach`)  
  - ST depression (`oldpeak`)  
- Certain categorical variables show strong predictive signals  

---

## 🤖 Models Used  

### 1. Logistic Regression  
- Linear baseline model  
- Interpretable and fast  
- Tuned using GridSearchCV  

---

### 2. Random Forest
- Ensemble learning method  
- Captures non-linear relationships  
- Provides feature importance  

---

## 📊 Evaluation Metrics  

- **Accuracy** → Overall correctness  
- **Precision** → Correct positive predictions  
- **Recall** → Ability to detect disease  
- **F1 Score** → Balance between precision & recall  
- **ROC-AUC** → Model’s discriminative ability  

---

## 🏆 Results  

### 🔥 Best Model: Logistic Regression (slightly higher ROC-AUC)

- **Accuracy:** 0.8689  
- **ROC-AUC:** 0.9578  

### Random Forest Performance:
- **Accuracy:** 0.8689  
- **ROC-AUC:** 0.9470  

---

## 📊 Model Comparison  

| Model                | Accuracy | ROC-AUC |
|---------------------|----------|--------|
| Logistic Regression ⭐ | 0.8689   | 0.9578 |
| Random Forest        | 0.8689   | 0.9470 |

---

## 📌 Feature Importance (Random Forest)

Top predictors of heart disease:

- `thal (defect type)`  
- `thalach (max heart rate)`  
- `ca (major vessels)`  
- `cp (chest pain type)`  
- `oldpeak`  
- `age`  

---

## 🔍 Model Refinement  

Reduced model using **Top 7 Features**:

Selected Features:
- thal_7.0  
- thalach  
- thal_3.0  
- ca  
- cp_4.0  
- oldpeak  
- age  

### Refined Model Performance:
- Accuracy: **0.8525**  
- ROC-AUC: **0.9405**  

📌 Insight:  
Slight drop in performance but significant reduction in complexity → more interpretable model.

---

## ⚡ Scalability  

- Used **GridSearchCV with `n_jobs=-1`** for parallel processing  
- Easily extendable to:
  - **Dask** (parallel computing)  
  - **Apache Spark (PySpark)** for big data  

---

## ⚠️ Challenges  

- Small dataset size  
- Missing values in key features  
- Risk of overfitting with complex models  
- Feature encoding increased dimensionality  

---

## 🚧 Limitations  

- Dataset is relatively small (303 samples)  
- No real-time or streaming data  
- Limited demographic diversity  
- No temporal (time-series) analysis  

---

## 🚀 Future Improvements and Alternatives  

- Use advanced models:
  - XGBoost / LightGBM  
- Apply feature selection techniques (RFE, SHAP)  
- Deploy model using:
  - FastAPI (API service)  
  - Streamlit (dashboard)  
- Integrate real-time health monitoring data  
- Improve interpretability using SHAP/LIME  

---

## 🧠 Key Takeaways  

- ROC-AUC is crucial for healthcare classification ✅  
- Feature importance helps clinical interpretability  
- Simpler models (Logistic Regression) can outperform complex ones  
- Proper preprocessing significantly improves results  

---

---

## 👨‍💻 Team  

- Kushal Niboriya
- Meet Modi
- Paras Verma
- Ayush Dudwe
- Krishna Agrawal 

---

## 📎 References  

- UCI Machine Learning Repository — Heart Disease Dataset  
- Scikit-learn Documentation  
- Medical literature on cardiovascular risk prediction  
