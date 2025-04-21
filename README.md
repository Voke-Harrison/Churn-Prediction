# BAN6800-Module-4-Business-Analytics-Model
# Shield360 Project - Customer Churn Prediction Model
---
### Project Objective

The primary goal of this project is to analyze and predict customer churn using machine learning models. By identifying customers who are likely to leave, telecom businesses can take proactive steps to improve retention and customer satisfaction.

The solution is developed in Python using Jupyter Notebooks, with models including:
- Logistic Regression
- Decision Tree
- Random Forest
- **Gradient Boosted Decision Trees (GBDT)**
- Multilayer Perceptron (MLP) - Neural Network

---
### GitHub Repository content
- The Cleaned Dataset - telco_churn_cleaned.csv
- Taco-Tel's Churn Prediction Model - Taco-Tel Churn Prediction Model.ipynb
- Previously Submited Taco-Tel's Exploratory Notebook - Taco-Tel Churn Prediction Data Exploration.ipynb
  
---
### Dataset Overview

The dataset contains customer demographics, account information, service usage, and churn status. It includes the following key columns (among others):

- Customer ID, Country, State, City, Zip Code
- Gender, Partner, Dependents, Tenure Months
- Internet Service, Tech Support, Streaming TV, Device Protection
- Monthly Charges, Total Charges, Total Revenue, CLTV
- Churn Label, Churn Value, Churn Reason, Customer Status
- One-hot encoded variables for contracts, offers, internet type, and payment methods

Total Columns (after cleaning): **67**

---
### Project Steps

#### 1. Data Cleaning & Preprocessing
- Removed duplicate columns
- Dropped irrelevant columns (e.g., Customer ID)
- Converted numeric fields (e.g., Total Charges) from string to float
- Label-encoded categorical features using LabelEncoder
- One-hot encoding applied to variables like contract type and payment method
- Scaled features using StandardScaler for models sensitive to feature magnitude

#### 3. Model Development
Models trained using a 80/20 train-test split with stratification:
- **Logistic Regression**
- **Decision Tree**
- **Random Forest**
- **Gradient Boosted Decision Trees**
- **Multilayer Perceptron (MLP) - Neural Network (Keras with ReLU and dropout layers)**

Model Evaluation Metrics:
- **F1 Score (macro)**
- **Recall Score (macro)**
- **AUC-ROC**
- **Confusion Matrix**

---

### Model Performance Summary

| Model             | F1 Score (Train) | F1 Score (Test) | Recall (Test) |
|------------------|------------------|------------------|----------------|
| GBDT              | 0.986            | **0.935**         | **0.924**        |
| Decision Tree     | 0.936            | 0.933            | 0.917          |
| Neural Network    | 0.976            | 0.930            | 0.920          |
| Random Forest     | 0.930            | 0.929            | 0.909          |
| Logistic Regression | 0.909          | 0.909            | 0.902          |

---

### Model Evaluation & Validation

- Evaluated models using test set metrics.
- Visualized ROC curves and confusion matrices.
- Checked for overfitting by comparing train vs. test F1 scores.
- GBDT provided the best balance of recall and F1, indicating high reliability and generalizability.
- Neural Network performed competitively and may be preferred in environments requiring deep learning deployment.

---

### Final Model Selection Criteria

| Criterion               | Description |
|------------------------|-------------|
| **F1 Score ≥ 0.90**    | Strong balance between precision and recall |
| **Recall ≥ 0.90**      | Captures at-risk customers with high accuracy |
| **AUC ≥ 0.90**         | Confident probability-based predictions |
| **Interpretability**   | GBDT preferred for feature importance transparency |

---

### Key Recommendations

- **Deploy GBDT model** in production for churn classification.
- Periodically retrain model to adjust for changes in customer behavior (concept drift).
- Explore hyperparameter tuning via GridSearchCV.
