# Assignment 2: Data Wrangling and Exploratory Analysis

## Student Project

This project applies NumPy, Pandas, and Matplotlib to explore and analyze a real-world customer churn dataset.

## Dataset

**Dataset Name:** Churn Modelling Dataset

**Source:** Kaggle
https://www.kaggle.com/datasets/shrutimechlearn/churn-modelling

**License:** Other (specified by the author)

The dataset contains information about 10,000 bank customers, including demographic and account-related information. It includes both numerical and categorical variables.

## Research Question

**What customer characteristics and account-related factors are associated with customer churn?**

## Project Structure

```text
KLab/
│
├── data/
│   ├── raw/
│   │   └── Churn_Modelling.csv
│   └── processed/
│       └── churn_cleaned_features.csv
│
├── notebooks/
│   └── assignment2.ipynb
│
├── reports/
│   ├── a2_chart1.png
│   ├── a2_chart2.png
│   ├── weekend-a2-report.md
│   └── weekend-a2-reflection.md
│
└── README.md
```

## Analysis Performed

The analysis includes:

* Dataset schema inspection
* Missing-value and duplicate checks
* Data cleaning
* GroupBy aggregation
* Merging group-level statistics back into the dataset
* Pivot table analysis of churn by geography and gender
* NumPy vectorized standardization of customer account balance
* Exploratory data visualizations

## Key Findings

Customer churn rates vary across geographical locations. The analysis also suggests that customers who exited the bank tend to be older than customers who remained.

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Jupyter Notebook
* VS Code

## How to Run

1. Clone the repository.
2. Create and activate a Python virtual environment.
3. Install the required dependencies:

```bash
pip install -r requirements.txt
```

4. Open and run:

```text
notebooks/assignment2.ipynb
```

# Car Price Classification — Premium vs Regular

## Project Overview

This project is a machine learning classification task completed as part of the kLab training programme.

The objective is to classify vehicles into two categories based on their characteristics:

* **Premium (1):** Vehicles whose prices fall within the highest 25% of the dataset.
* **Regular (0):** Vehicles whose prices fall below the Premium threshold.

The project demonstrates the complete machine learning workflow, from data cleaning and preprocessing to model training and evaluation.

## Dataset

The dataset contains information about vehicles, including:

* **Name** — Vehicle name
* **Year** — Manufacturing year
* **Miles** — Mileage
* **Price** — Vehicle price

For classification, `Year` and `Miles` were used as input features.

`Price` was used to create the target variable (`Premium`) but was excluded from the model features to prevent **data leakage**.

## Data Cleaning

Before training the models, the dataset was checked for invalid values.

An invalid vehicle year was identified because it fell outside the reasonable range of **1900–2026**. Invalid year records were removed before model training.

## Target Variable

The `Premium` target was created using the **75th percentile of vehicle prices**.

```text
Premium = 1 → Price >= 75th percentile
Premium = 0 → Price < 75th percentile
```

This creates a binary classification problem.

## Machine Learning Models

Two classification algorithms were implemented and compared:

### 1. Logistic Regression

Logistic Regression was used as the baseline classification model.

Feature scaling was performed using `StandardScaler` before training the model.

### 2. Random Forest

Random Forest was used as a second classification model to compare its performance with Logistic Regression.

Random Forest does not require feature scaling.

## Model Evaluation

The models were evaluated using the following classification metrics:

* **Accuracy**
* **Precision**
* **Recall**
* **F1-Score**
* **ROC-AUC**
* **Confusion Matrix**

A ROC curve and feature-importance analysis were also performed.

## Project Structure

```text
kLab/
│
├── data/
│   └── raw/
│       └── carvana.csv
│
├── notebooks/
│   └── assignment3.ipynb
│
├── src/
│   └── assignment.py
│
└── README.md
```

## Tools and Technologies

* Python
* Pandas
* NumPy
* Scikit-learn
* Matplotlib
* Jupyter Notebook
* Visual Studio Code
* Git & GitHub

## Key Learning Outcomes

Through this project, I practised:

* Data exploration and cleaning
* Handling invalid data
* Feature selection
* Creating a classification target
* Train/test splitting
* Feature scaling
* Logistic Regression
* Random Forest classification
* Classification evaluation metrics
* Confusion matrices
* ROC curves
* Feature importance
* Git and GitHub version control

## Author

**Abijuru Divine**

Business Information Technology Student
University of Kigali
