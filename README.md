# Customer Churn Prediction

A machine learning project that predicts whether a customer is likely to churn using **Logistic Regression, Random Forest, and XGBoost**.

The project includes data preprocessing, exploratory data analysis, model training, evaluation, and a **Streamlit web application** for interactive churn prediction and model interpretation using SHAP.

---

## 📌 Project Overview

Customer churn refers to customers discontinuing their services. Predicting customer churn helps businesses identify customers who are likely to leave and take preventive actions.

This project uses the **Telco Customer Churn dataset** to train and compare multiple machine learning models.

The trained models are integrated into a Streamlit application where users can enter customer details and obtain:

* Churn prediction
* Churn probability
* Selected model information
* SHAP-based prediction explanation
* Model performance comparison
* Feature importance
* Business insights

---

## 🚀 Features

* Customer churn prediction
* Three machine learning models:

  * Logistic Regression
  * Random Forest
  * XGBoost
* Interactive Streamlit interface
* Model selection
* Churn probability prediction
* SHAP-based prediction explanations
* Feature importance visualization
* Model performance comparison
* Business insights for customer retention

---

## 🧠 Machine Learning Models

The project uses the following models:

### 1. Logistic Regression

A linear classification algorithm used as a baseline model for predicting customer churn.

### 2. Random Forest

An ensemble learning algorithm that combines multiple decision trees to improve prediction performance.

### 3. XGBoost

A gradient boosting algorithm designed for efficient and accurate classification.

---

## 📊 Model Performance

The models were evaluated using ROC-AUC, F1 Score, Precision, and Recall.

| Model               | ROC-AUC | F1 Score | Precision | Recall |
| ------------------- | ------: | -------: | --------: | -----: |
| Logistic Regression |    0.86 |     0.64 |      0.52 |   0.84 |
| Random Forest       |    0.85 |     0.65 |      0.56 |   0.78 |
| XGBoost             |    0.85 |     0.64 |      0.53 |   0.80 |

---

## 🗂️ Project Structure

```text
Customer-churn-prediction/
│
├── app/
│   └── app.py
│
├── data/
│   └── WA_Fn-UseC_-Telco-Customer-Churn.csv
│
├── models/
│   ├── logistic_model.pkl
│   ├── rf_model.pkl
│   └── xgb_model.pkl
│
├── notebook/
│   └── churn.ipynb
│
├── README.md
└── requirements.txt
```

---

## 📥 Dataset

This project uses the **Telco Customer Churn dataset**.

### Dataset Source

The dataset can be downloaded from Kaggle:

https://www.kaggle.com/datasets/blastchar/telco-customer-churn

### Dataset Filename

After downloading the dataset, the CSV file should be named:

```text
WA_Fn-UseC_-Telco-Customer-Churn.csv
```

### Dataset Location

Place the downloaded CSV file inside the project's `data` directory:

```text
Customer-churn-prediction/
└── data/
    └── WA_Fn-UseC_-Telco-Customer-Churn.csv
```

If the `data` folder does not exist, create it manually.

### Windows PowerShell

From the project root:

```powershell
mkdir data
```

Then copy the downloaded CSV file into:

```text
data/WA_Fn-UseC_-Telco-Customer-Churn.csv
```

### macOS / Linux

From the project root:

```bash
mkdir -p data
```

Then copy the downloaded CSV file into:

```text
data/WA_Fn-UseC_-Telco-Customer-Churn.csv
```

> **Important:** Make sure the filename and folder location are exactly as shown above.

---

## ⚙️ Installation and Setup

### 1. Clone the Repository

Open a terminal or command prompt and run:

```bash
git clone https://github.com/SAQIB-KHAN-25/Customer-churn-prediction.git
```

Move into the project directory:

```bash
cd Customer-churn-prediction
```

---

### 2. Create a Virtual Environment

It is recommended to create a virtual environment before installing the dependencies.

#### Windows

```powershell
python -m venv venv
```

Activate it:

```powershell
venv\Scripts\activate
```

#### macOS / Linux

```bash
python3 -m venv venv
```

Activate it:

```bash
source venv/bin/activate
```

---

### 3. Install Dependencies

Install all required Python packages using:

```bash
pip install -r requirements.txt
```

---

### 4. Add the Dataset

Download the Telco Customer Churn dataset from Kaggle and place it at:

```text
data/WA_Fn-UseC_-Telco-Customer-Churn.csv
```

Your project should now contain:

```text
Customer-churn-prediction/
├── app/
│   └── app.py
├── data/
│   └── WA_Fn-UseC_-Telco-Customer-Churn.csv
├── models/
│   ├── logistic_model.pkl
│   ├── rf_model.pkl
│   └── xgb_model.pkl
├── notebook/
│   └── churn.ipynb
├── README.md
└── requirements.txt
```

---

## ▶️ Running the Application

The Streamlit application is located inside the `app` folder.

From the project root, run:

```bash
streamlit run app/app.py
```

After running the command, Streamlit will provide a local URL, usually similar to:

```text
http://localhost:8501
```

Open the URL in your web browser to use the application.

---

## 🖥️ Using the Application

### Prediction

The Prediction tab allows users to:

1. Select a machine learning model.
2. Enter customer information.
3. Predict whether the customer is likely to churn.
4. View the predicted churn probability.
5. View a SHAP-based explanation of the prediction.

Available models:

```text
Logistic Regression
Random Forest
XGBoost
```

The SHAP explanation corresponds to the **model selected by the user**.

---

## 📈 Model Insights

The Model Insights section provides information about the trained models, including:

* Feature importance
* SHAP-based model interpretation
* Model performance comparison
* ROC-AUC
* F1 Score
* Precision
* Recall

These insights help understand which customer characteristics have an important influence on churn prediction.

---

## 🔍 Technologies Used

### Programming Language

* Python

### Machine Learning

* Scikit-learn
* XGBoost

### Data Processing

* Pandas
* NumPy

### Visualization

* Matplotlib
* SHAP

### Web Application

* Streamlit

### Model Serialization

* Joblib

---

## 📚 Project Workflow

```text
Dataset
   ↓
Data Cleaning
   ↓
Exploratory Data Analysis
   ↓
Data Preprocessing
   ↓
Train/Test Split
   ↓
Model Training
   ↓
Model Evaluation
   ↓
Model Saving
   ↓
Streamlit Application
   ↓
Churn Prediction
   ↓
SHAP Explanation
```

---

## 🎯 Objectives

The main objectives of this project are:

* To analyze customer churn behavior.
* To preprocess customer data for machine learning.
* To train multiple classification models.
* To compare model performance.
* To predict customer churn probability.
* To provide interpretable model predictions using SHAP.
* To provide useful insights that can support customer retention strategies.

---

## 💡 Business Insights

Customer churn prediction can help businesses:

* Identify customers who are likely to leave.
* Understand important factors associated with churn.
* Prioritize high-risk customers.
* Develop targeted retention strategies.
* Improve customer satisfaction.
* Reduce customer acquisition and replacement costs.

---

## 📝 Notebook

The complete data analysis, preprocessing, model training, evaluation, and experimentation can be found in:

```text
notebook/churn.ipynb
```

---

## 📦 Trained Models

The trained machine learning models are stored in the `models` directory:

```text
models/
├── logistic_model.pkl
├── rf_model.pkl
└── xgb_model.pkl
```

These models are loaded by the Streamlit application for making predictions.

---

## 🛠️ Troubleshooting

### `FileNotFoundError` for the dataset

Make sure the dataset exists at exactly:

```text
data/WA_Fn-UseC_-Telco-Customer-Churn.csv
```

Also make sure the filename has not been changed.

---

### `streamlit: command not found`

Make sure your virtual environment is activated and Streamlit is installed:

```bash
pip install -r requirements.txt
```

You can also run:

```bash
python -m streamlit run app/app.py
```

---

### Model file not found

Make sure the following files exist:

```text
models/logistic_model.pkl
models/rf_model.pkl
models/xgb_model.pkl
```

---

## 👨‍💻 Author

**Saqib Ahmed Khan**

Information Science and Engineering
Visvesvaraya Technological University (VTU)

---

## 📄 License

This project is intended for educational and learning purposes.
