# Final-Project

# 🚀 Lung Cancer Prediction Using Clinical, Biochemical, and Genetic Data

## 📌 Project Overview
Lung cancer remains one of the leading causes of cancer-related deaths worldwide. Early detection is crucial for improving survival rates. This project aims to develop a **machine learning-based predictive model** that can assist in identifying lung cancer cases using **demographic, clinical, biochemical, and genetic data**.

By leveraging **supervised learning techniques**, this project provides an **automated and interpretable approach** to lung cancer detection, potentially aiding healthcare professionals in decision-making.

---

## 📂 Dataset Overview
The dataset consists of **8,796 patient records** with **14 key features**, categorized into the following groups:

### 1️⃣ Demographics
- **Age** (Numeric)  
- **Gender** (Categorical: Male/Female)  

### 2️⃣ Medical History
- **Smoking History** (Categorical: Yes/No)  
- **Family History** (Categorical: Yes/No)  
- **Treatment History** (Categorical: Radiotherapy, Chemotherapy, None)  

### 3️⃣ Biochemical Data
- **ctDNA Concentration (ng/mL)** (Numeric)  
- **VOC1 Concentration (ppm)** (Numeric)  
- **VOC2 Concentration (ppm)** (Numeric)  

### 4️⃣ Genetic Data
- **Mutation Type** (Categorical: Deletion, Insertion)  
- **Gene** (Categorical, with missing values)  

### 5️⃣ Clinical Measurements
- **Tumor Size (cm)** (Numeric)  
- **Biopsy Result** (Categorical: Positive/Negative)  

### 🎯 Target Variable
- **Lung Cancer** (Binary Classification: Yes/No)  

---

## 🛠 Project Workflow
This project follows a **structured machine learning pipeline**, ensuring efficiency, interpretability, and robustness in the predictive model.

### **Step 1: Data Preprocessing & Cleaning**
✔ **Handled Missing Values**: Used mode imputation for categorical variables (**Gene, Mutation Type, Treatment History**).  
✔ **Handled Outliers**: Applied **Z-score analysis** to remove extreme values.  
✔ **Feature Scaling**: Standardized numerical features using **StandardScaler()**.  
✔ **Class Balancing**: Applied **SMOTE (Synthetic Minority Oversampling Technique)** to balance "Yes" and "No" cases.  

### **Step 2: Exploratory Data Analysis (EDA)**
✔ **Class Distribution Visualization**: Checked the proportion of lung cancer-positive and negative cases.  
✔ **Feature Correlation Analysis**: Identified key predictors like **Tumor Size, Biopsy Result, and ctDNA Concentration**.  
✔ **Histograms & Boxplots**: Compared feature distributions for lung cancer-positive vs. negative patients.  

### **Step 3: Model Training & Evaluation**
The dataset was split into **80% training and 20% testing**, and five machine learning models were trained:

| Model               | Accuracy | Precision | Recall | F1 Score | ROC AUC |
|---------------------|----------|------------|------------|-------------|-------------|
| **Logistic Regression** | 56.6%   | 100%       | 48.4%    | 65.2%  | 0.96 |
| **K-Nearest Neighbors (KNN)** | 82.4%   | 84.2%    | 97.4%    | 90.3%  | 0.50 |
| **Support Vector Machine (SVM)** | 84.1%   | 84.1%    | 100%     | 91.4%  | 0.61 |
| **Decision Tree** | 91.0%   | 94.9%    | 94.4%    | 94.7%  | 0.83 |
| **Random Forest** | **93.0%**  | **93.3%**  | **98.8%**  | **95.9%**  | **0.97** |

✔ **Random Forest outperformed all models**, achieving the highest accuracy and recall, making it the best model for this task.  

### **Step 4: Model Optimization & Hyperparameter Tuning**
✔ **Fine-tuned Random Forest parameters** using `GridSearchCV` to find the best configuration:

```yaml
Best Parameters: {'max_depth': 20, 'min_samples_leaf': 1, 'min_samples_split': 2, 'n_estimators': 50}
