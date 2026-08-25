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
