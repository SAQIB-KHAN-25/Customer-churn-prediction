# 📊 Customer Churn Prediction App

An end-to-end **Machine Learning project** that predicts customer churn probability using customer demographics, account information, subscribed services, and billing data.

The project focuses not only on model training, but on the **complete data science workflow** — from understanding the problem and performing EDA to preprocessing, feature engineering, model comparison, threshold optimization, explainability, and deployment.

---

## 📌 Project Overview

Customer churn is an important business problem for subscription-based companies. Identifying customers who are likely to leave can help businesses design targeted retention strategies.

This project develops a machine learning system that:

* Analyzes customer data
* Performs exploratory data analysis
* Preprocesses numerical and categorical features
* Handles class imbalance
* Trains and compares multiple ML models
* Optimizes the classification threshold
* Explains predictions using SHAP
* Provides real-time churn probability predictions
* Deploys the trained model through Streamlit

The goal is to demonstrate how a **real-world data science project can be approached from problem definition to deployment**.

---

# 🎯 Problem Statement

Given information about a customer, predict whether the customer is likely to churn.

### Input

The model uses information such as:

* Customer demographics
* Tenure
* Contract type
* Internet service
* Payment method
* Subscribed services
* Monthly charges
* Total charges
* Account information

### Output

The application provides:

* Churn prediction
* Churn probability
* Model-based insights
* SHAP explanations

---

# 📂 Dataset

This project uses the **Telco Customer Churn Dataset**.

**Dataset:**
https://www.kaggle.com/datasets/blastchar/telco-customer-churn

### Dataset Statistics

* **7,043 customer records**
* **21 features**
* Target variable: `Churn`

### Feature Categories

| Category              | Examples                                            |
| --------------------- | --------------------------------------------------- |
| Customer Demographics | Gender, SeniorCitizen, Partner, Dependents          |
| Account Information   | Tenure, Contract, Billing Method                    |
| Services              | Internet Service, Streaming, Security, Tech Support |
| Billing               | Monthly Charges, Total Charges                      |
| Target                | Churn                                               |

---

# 🔄 Data Science Workflow

The project follows an end-to-end machine learning workflow:

```text
Business Understanding
        ↓
Data Collection
        ↓
Data Understanding
        ↓
Exploratory Data Analysis
        ↓
Data Cleaning
        ↓
Feature Engineering
        ↓
Preprocessing
        ↓
Train/Test Split
        ↓
Model Training
        ↓
Model Comparison
        ↓
Class Imbalance Handling
        ↓
Threshold Optimization
        ↓
Model Explainability
        ↓
Deployment
```

---

# 🔎 Exploratory Data Analysis

EDA was performed to understand customer behavior and identify patterns associated with churn.

Areas explored include:

* Churn distribution
* Customer tenure
* Contract types
* Monthly charges
* Internet service
* Value-added services
* Customer demographics
* Relationship between services and churn

### Important Observations

Customers with:

* Shorter tenure
* Month-to-month contracts
* Higher monthly charges
* Fiber optic internet service
* Lack of security and technical support services

show higher churn rates in the dataset.

---

# 🛠️ Data Preprocessing

The dataset contains both numerical and categorical variables, so separate preprocessing strategies were applied.

## Numerical Features

Examples:

```text
Tenure
MonthlyCharges
TotalCharges
```

Processing:

* Missing-value handling
* Standard scaling

## Categorical Features

Examples:

```text
Gender
Contract
InternetService
PaymentMethod
Service-related features
```

Processing:

* Missing-value handling
* One-hot encoding

All preprocessing is handled using **Scikit-learn's `ColumnTransformer`**, making the preprocessing pipeline reproducible and consistent between training and prediction.

---

# ⚙️ Feature Engineering

Feature engineering was used to prepare the raw customer information for machine learning.

The process focuses on transforming customer attributes into representations that can be effectively used by the models.

Important customer characteristics include:

* Tenure
* Contract type
* Monthly charges
* Total charges
* Internet service
* Subscription services
* Security services
* Technical support

---

# 🤖 Machine Learning Models

Three machine learning algorithms were evaluated.

## 1. Logistic Regression

Used as an interpretable baseline model.

Advantages:

* Simple
* Interpretable
* Effective baseline
* Useful for understanding feature relationships

---

## 2. Random Forest

An ensemble learning model capable of capturing non-linear relationships.

Advantages:

* Handles non-linear patterns
* Ensemble-based
* Robust model
* Provides useful feature importance information

---

## 3. XGBoost

A gradient boosting algorithm used for more advanced modeling.

The implementation uses:

```text
scale_pos_weight
```

to address class imbalance.

Additional learning and regularization parameters were considered during model development.

---

# 📈 Model Performance

The evaluated models produced the following results:

| Model               | ROC-AUC | F1 Score | Precision | Recall |
| ------------------- | ------: | -------: | --------: | -----: |
| Logistic Regression |    0.86 |     0.64 |      0.52 |   0.84 |
| Random Forest       |    0.85 |     0.65 |      0.56 |   0.78 |
| XGBoost             |    0.85 |     0.63 |      0.55 |   0.75 |

### Metrics Used

**ROC-AUC**
Measures how effectively the model distinguishes between churn and non-churn customers across classification thresholds.

**Precision**
Measures how many customers predicted as churners actually churned.

**Recall**
Measures how many actual churners were successfully identified.

**F1 Score**
Provides a balance between precision and recall.

---

# ⚖️ Class Imbalance & Threshold Optimization

Customer churn datasets commonly contain fewer churned customers than non-churned customers.

Therefore, accuracy alone is not sufficient for evaluating the model.

Instead, the project considers:

* Precision
* Recall
* F1 Score
* ROC-AUC

### Threshold Optimization

Rather than relying only on the default:

```text
Threshold = 0.50
```

different classification thresholds were evaluated.

This allows the business to adjust the model according to its preferred balance between:

```text
False Positives
        ↕
False Negatives
```

For example, a business that wants to identify more potentially churning customers may prefer a threshold that increases recall.

---

# 🔍 Model Explainability with SHAP

Machine learning predictions are more useful when users can understand **why** a prediction was made.

This project uses **SHAP (SHapley Additive Explanations)** to interpret the model.

SHAP is used to:

* Explain individual predictions
* Identify important features
* Understand global feature importance
* Analyze factors contributing to churn probability

### Key Insights

The analysis identified patterns such as:

* 📉 Lower tenure being associated with higher churn risk
* 📉 Month-to-month contracts being strongly associated with churn
* 📈 Higher monthly charges being associated with increased churn probability
* ❌ Lack of security and technical-support services being associated with higher churn

---

# 💡 Business Insights

The analysis suggests several areas businesses could investigate for customer retention.

### Contract Type

Customers on month-to-month contracts show higher churn probability.

### Customer Tenure

Customers with shorter tenure are more likely to churn.

### Monthly Charges

Higher monthly charges are associated with increased churn.

### Internet Service

Customers using fiber optic service show higher churn rates in this dataset.

### Value-Added Services

Customers without services such as:

* Online Security
* Tech Support
* Device Protection

show higher churn rates.

---

# 💼 Potential Business Applications

The model can support customer-retention workflows such as:

```text
Customer Data
      ↓
Churn Probability
      ↓
Risk Identification
      ↓
Customer Segmentation
      ↓
Retention Strategy
```

Possible applications include:

* Identifying high-risk customers
* Prioritizing retention campaigns
* Designing targeted offers
* Investigating service-related churn
* Supporting customer success teams

---

# 🌐 Deployment

The application is deployed using **Streamlit**.

Users can enter customer information through the web interface and receive a real-time prediction.

### Application Features

* Customer information input
* Churn probability prediction
* Model prediction
* SHAP-based explanation
* Interactive interface

---

# 🧰 Tech Stack

### Programming

* Python

### Data Analysis

* Pandas
* NumPy
* Matplotlib

### Machine Learning

* Scikit-learn
* XGBoost

### Explainability

* SHAP

### Deployment

* Streamlit

### Model Persistence

* Joblib

---

# 📁 Project Structure

```text
customer-churn-prediction/
│
├── data/
│   └── Telco_customer_churn
│
├── notebooks/
│   └── churn_analysis.ipynb
│
├── models/
│   └── trained_model.pkl
│
├── app.py
├── requirements.txt
├── README.md
└── .gitignore
```

---

# ⚙️ Installation

## 1. Clone the Repository

```bash
git clone https://github.com/<SAQIB-KHAN-25>/customer-churn-prediction.git
```

Move into the project directory:

```bash
cd customer-churn-prediction
```

---

## 2. Create a Virtual Environment

```bash
python -m venv venv
```

### Windows

```bash
venv\Scripts\activate
```

### macOS / Linux

```bash
source venv/bin/activate
```

---

## 3. Install Dependencies

```bash
pip install -r requirements.txt
```

---

# ▶️ Run the Application

Start the Streamlit application:

```bash
streamlit run app.py
```

The application will open in your browser.

---

# 📦 Requirements

Example dependencies include:

```text
pandas
numpy
scikit-learn
xgboost
shap
matplotlib
streamlit
joblib
```

Install them using:

```bash
pip install -r requirements.txt
```

---

# 📊 Project Learning Outcomes

This project was developed to understand the practical workflow of a data science project rather than focusing only on model accuracy.

Through this project, the following concepts were practiced:

### Data Understanding

* Understanding the business problem
* Understanding the dataset
* Identifying target and predictor variables

### EDA

* Exploring distributions
* Identifying patterns
* Studying relationships between features and target
* Understanding churn behavior

### Data Preprocessing

* Missing-value handling
* Numerical feature scaling
* Categorical encoding
* Building preprocessing pipelines

### Machine Learning

* Baseline model development
* Ensemble models
* Gradient boosting
* Model comparison
* Evaluation metrics

### Imbalanced Classification

* Understanding class imbalance
* Precision vs recall
* Threshold tuning

### Explainable AI

* SHAP
* Individual prediction explanations
* Feature importance

### Deployment

* Saving trained models
* Building a Streamlit interface
* Deploying an ML application

---

# 🚧 Future Improvements

Potential improvements include:

* Hyperparameter optimization
* Cross-validation
* Additional feature engineering
* More advanced ensemble techniques
* Model monitoring
* Automated retraining
* Customer segmentation
* Cost-sensitive evaluation
* Integration with a customer-management system
* Improved visualization and analytics dashboard

---

# 📌 Conclusion

This project demonstrates an **end-to-end approach to building a machine learning solution for customer churn prediction**.

Rather than treating machine learning as simply:

```text
Data → Model → Accuracy
```

the project follows a broader workflow:

```text
Business Problem
      ↓
Data Understanding
      ↓
EDA
      ↓
Preprocessing
      ↓
Feature Engineering
      ↓
Model Development
      ↓
Evaluation
      ↓
Threshold Optimization
      ↓
Explainability
      ↓
Deployment
```

The project demonstrates how predictive modeling can be combined with **data analysis, explainability, and deployment** to create a practical machine learning application.

---

## ⭐ If you found this project useful

Feel free to explore the repository, try the live application, and experiment with the models and preprocessing pipeline.

**Built with Python, Scikit-learn, XGBoost, SHAP & Streamlit.**
