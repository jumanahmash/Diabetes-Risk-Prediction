# Diabetes Risk Prediction 🩸📊

**Course:** IS316: Data Science | King Saud University (2nd Semester 1447 H)  
**Supervised By:** Shatha Al Tamami  

## 👥 Team Members (Group 3)
* Jumanah Ibrahim
* Arwa Almutairi
* Dana Alturki
* Shatha Munif

---

## 📌 Project Overview
The increasing prevalence of diabetes has become a major global health concern. Early detection is often missed, leading to severe complications. The objective of this project is to build a robust machine learning model capable of classifying individuals into different diabetes risk categories (**Low Risk, Prediabetes, High Risk**) based on health indicators and lifestyle features. 

By predicting risk levels early, this project aims to support healthcare providers in early diagnosis and preventive medical intervention.

## 📂 Dataset
* **Source:** Kaggle
* **Size:** 6,000 records
* **Features:** Includes age, BMI, fasting glucose levels, HbA1c, daily calorie intake, triglyceride levels, sleep hours, and other medical/lifestyle data.

## 🔍 Exploratory Data Analysis (EDA) & Preprocessing
During **Phase 1**, we conducted extensive EDA to understand the underlying patterns in the dataset:
* **Class Distribution:** The majority of cases fall into the *Low Risk* category, highlighting a slight class imbalance that needed to be monitored.
* **Correlations:** * Strong positive correlations were found between **BMI, waist circumference**, and overall diabetes risk.
  * **Fasting glucose** highly correlates with **HbA1c**.
  * **Sleep hours** showed a negative correlation with several risk features, indicating poorer health with less sleep.
* **Data Cleaning:** Outliers identified in the glucose data via boxplots were properly handled to prepare the data for modeling.

## 🤖 Modeling & Evaluation
In **Phase 2**, we trained and evaluated three machine learning classification models. 

### Addressing Data Leakage
During initial training, models achieved an unrealistic 100% accuracy. This was identified as **Data Leakage** caused by the inclusion of a `diabetes_risk_score` feature. After removing this leaky feature, our models produced highly realistic and reliable results.

### Results
The models successfully captured real-world patterns (heavily utilizing Glucose and BMI features). Performance metrics after fixing data leakage:

| Model | Accuracy | Precision | Recall | F1-Score |
|-------|----------|-----------|--------|----------|
| **Support Vector Machine (SVM)** | **~0.915** | 0.92 | 0.91 | 0.91 |
| **Random Forest** *(Selected Model)* | **~0.913** | 0.91 | 0.91 | 0.91 |
| **Logistic Regression** | ~0.810 | 0.81 | 0.80 | 0.72 |

**Conclusion:** **Random Forest** was selected as our final model due to its strong, stable performance, high accuracy (~91%), and robustness in handling this classification task.

## 🚧 Limitations & Future Work
While the models performed exceptionally well, there is room for expansion:
* **Limitations:** The dataset contains a slight class imbalance affecting minority class predictions. Additionally, it lacks crucial real-world features like family history and detailed lifestyle habits.
* **Future Work:** * Apply hyperparameter tuning to further optimize model performance.
  * Implement techniques like **SMOTE** to handle class imbalance.
  * Incorporate a wider variety of real-world features for broader clinical applicability.

---
*This repository contains the Jupyter Notebooks for Phase 1 and 2, along with the final presentation and report documentation.*
