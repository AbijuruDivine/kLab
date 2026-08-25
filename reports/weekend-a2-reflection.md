**#Assignment 2 Reflection**

**1. Which transform took the longest to get right, and why?**

The GroupBy and Merge transformation took the longest to understand and complete correctly. I needed to understand how to first group customers by geographical location, calculate aggregate statistics such as average account balance and average estimated salary, and then merge those results back into the main dataframe.

The challenging part was understanding how the grouped dataframe was different from the original dataframe and making sure that the `Geography` column could be used correctly as the common key during the merge. However, after completing the transformation, I understood how GroupBy can be used to create useful group-level information and how Merge can add that information back to the original dataset.

## 2. What would you do differently with another dataset?

If I had another dataset to analyze, I would spend more time understanding the dataset before starting the transformations. I would first examine the meaning of each column, identify possible data quality issues, and think more carefully about the questions I want to answer.

I would also explore additional relationships between variables and try different feature engineering techniques. This assignment helped me understand that data cleaning and exploratory analysis are important before drawing conclusions from a dataset.