# Assignment 2: Customer Churn Analysis Report

## Question Explored

This analysis explored the question: **What customer characteristics and account-related factors are associated with customer churn?**

The analysis used the Churn Modelling dataset, which contains information about 10,000 bank customers. The dataset includes demographic information such as age, gender, and geographical location, as well as account-related variables including credit score, account balance, number of products, credit card ownership, activity status, estimated salary, and whether the customer exited the bank.

## Data Preparation and Analysis

The dataset was examined for missing values, data type issues, and duplicate records. No missing values were found, so no imputation or removal of records was necessary. Identifier columns (`RowNumber`, `CustomerId`, and `Surname`) were removed because they do not provide useful information for analyzing customer churn.

Feature engineering was performed using Pandas. Customers were grouped by geographical location to calculate the average account balance and average estimated salary for each geographical group. These group-level statistics were then merged back into the main dataframe. A pivot table was also created to examine differences in churn rates across geography and gender.

In addition, NumPy was used to standardize the `Balance` column using a vectorized z-score transformation. The resulting standardized values were added to the dataset as a new feature called `BalanceStandardized`.

## Findings

The analysis showed that customer churn rates vary across geographical locations. **Figure 1 (`a2_chart1.png`)** illustrates these differences and makes it possible to identify the geographical groups with relatively higher and lower customer churn rates.

The analysis also compared the age distributions of customers who stayed with the bank and those who exited. **Figure 2 (`a2_chart2.png`)** suggests that customers who exited tend to be older than those who remained with the bank.

These findings indicate that demographic characteristics, particularly geographical location and age, may be associated with customer churn. However, the analysis is exploratory and does not prove that these characteristics directly cause customers to leave.

## Limitation

One limitation of this analysis is that the dataset shows relationships between variables but does not provide detailed information about why individual customers decided to leave. Important factors such as customer satisfaction, quality of service, complaints, or interactions with competitors are not included. Therefore, the findings should be interpreted as associations rather than direct causes of customer churn.

## Visualizations

* **Figure 1:** `a2_chart1.png` — Customer churn rates vary across geographic locations.
* **Figure 2:** `a2_chart2.png` — Customers who churn tend to be older than those who stay.
