# Decision Tree Classification from Scratch

**Name:** Abijuru Divine
**Project:** Decision Tree Classification from Scratch
**Dataset:** `bankloan.csv`


## 1. Introduction

This project implements a Decision Tree classification algorithm from scratch using Python.

The main objective is to understand and demonstrate how a Decision Tree works internally without using a pre-built machine learning model such as `DecisionTreeClassifier` from Scikit-learn.

The implementation covers the major stages of Decision Tree classification, including data preparation, Gini Impurity calculation, finding the best feature and threshold for splitting the data, recursively constructing the tree, making predictions, and evaluating the model's performance.

The Decision Tree was built with a maximum depth of **3** to control the complexity of the model and reduce the risk of overfitting.


## 2. Dataset Description

The dataset used in this project is the `bankloan.csv` dataset.

The dataset contains information about customers and their loan-related characteristics. The objective of the classification task is to use the available customer information to predict the target class.

The dataset was divided into two parts:

* **Training dataset:** Used to train and construct the Decision Tree.
* **Testing dataset:** Used to evaluate the performance of the completed Decision Tree.

The test dataset was kept separate from the training process so that the model could be evaluated on observations it had not used while learning the decision rules.


## 3. Data Preparation

Before building the Decision Tree, the dataset was prepared for the classification task.

The main preparation steps included:

1. Loading the `bankloan.csv` dataset.
2. Inspecting the dataset and its variables.
3. Selecting the input features.
4. Selecting the target variable.
5. Dividing the data into training and testing datasets.

The training data was used to identify the best decision rules, while the testing data was used only after the model had been constructed.


## 4. Decision Tree Methodology

### 4.1 Gini Impurity

Gini Impurity was used to measure the level of class mixing within a group of observations.

The formula for Gini Impurity is:

$$
Gini = 1 - \sum_{i=1}^{n} p_i^2
$$

where $p_i$ represents the proportion of observations belonging to class $i$.

A lower Gini Impurity indicates that the observations in a group are more homogeneous.

For each possible split, the Gini Impurity of the resulting left and right groups was calculated. The weighted impurity of the two groups was then used to determine the quality of the split.


### 4.2 Finding the Best Split

The algorithm examines the available features and possible threshold values to determine the best way to divide the training data.

For each possible feature and threshold, the observations are divided into two groups:

* **Left group:** Feature value is less than or equal to the threshold.
* **Right group:** Feature value is greater than the threshold.

The split with the lowest weighted Gini Impurity is selected as the best split.

This process allows the Decision Tree to identify the questions that provide the greatest separation between the target classes.


### 4.3 Recursive Tree Construction

After finding the best split, the dataset is divided into two branches.

The same process is then repeated recursively for each branch. This creates the structure of the Decision Tree.

The tree stops growing when one of the following conditions is met:

* All observations in a node belong to the same class.
* The maximum tree depth has been reached.
* No useful split can be found.

For this project, the maximum tree depth was set to **3**.

The tree was constructed using the following implementation:

```python
tree = build_tree(
    X_train,
    y_train,
    max_depth=3
)

print("Decision Tree built successfully.")
```

The resulting tree contains decision nodes and leaf nodes. Decision nodes contain a feature and threshold, while leaf nodes contain the final prediction.


### 4.4 Prediction

After constructing the Decision Tree, the model was used to make predictions on the test dataset.

Each test observation was passed through the tree starting from the root node.

At every decision node, the observation was directed to either the left or right branch according to the learned threshold.

The process continued until a leaf node was reached. The prediction stored at the leaf node was then returned as the predicted class.


## 5. Model Evaluation

The completed Decision Tree was evaluated using several classification metrics.

These metrics were calculated manually without using Scikit-learn's built-in evaluation functions.

### 5.1 Accuracy

Accuracy measures the proportion of all test observations that were classified correctly.

$$
Accuracy = \frac{TP + TN}{TP + TN + FP + FN}
$$

where:

* **TP** = True Positives
* **TN** = True Negatives
* **FP** = False Positives
* **FN** = False Negatives


### 5.2 Precision

Precision measures how many observations predicted as positive were actually positive.

$$
Precision = \frac{TP}{TP + FP}
$$

A high precision means that the model produces relatively few false-positive predictions.


### 5.3 Recall

Recall measures how many of the actual positive observations were correctly identified by the model.

$$
Recall = \frac{TP}{TP + FN}
$$

A high recall means that the model successfully identifies most of the actual positive cases.


### 5.4 F1-Score

The F1-score combines precision and recall into a single performance measure.

$$
F1 = 2 \times \frac{Precision \times Recall}{Precision + Recall}
$$

The F1-score is useful when both precision and recall are important.


## 6. Results

The Decision Tree was evaluated on the test dataset.

The model was configured with a maximum depth of **3**.

| Metric    |     Result |
| --------- | ---------: |
| Accuracy  | **97.80%** |
| Precision | **97.26%** |
| Recall    | **78.02%** |
| F1-Score  | **86.59%** |

These results indicate that the model achieved a high overall classification accuracy.

---

## 7. Confusion Matrix

The confusion matrix produced by the model was:

|              | Predicted 0 | Predicted 1 |
| ------------ | ----------: | ----------: |
| **Actual 0** |     **907** |       **2** |
| **Actual 1** |      **20** |      **71** |

The individual values are:

* **True Negatives (TN): 907**
* **False Positives (FP): 2**
* **False Negatives (FN): 20**
* **True Positives (TP): 71**

The model correctly classified **907 observations as class 0** and **71 observations as class 1**.

It incorrectly classified **2 class 0 observations as class 1** and **20 class 1 observations as class 0**.

The confusion matrix contains a total of **1,000 test observations**.


## 8. Discussion

The Decision Tree achieved an overall accuracy of **97.80%**, indicating strong classification performance on the test dataset.

The model achieved a precision of **97.26%**. This means that when the model predicted the positive class, it was correct most of the time. The high precision is supported by the very small number of false positives, with only **2 false-positive predictions**.

The recall was **78.02%**, which is lower than the precision. This indicates that although the model was highly reliable when predicting the positive class, it did not identify all actual positive observations. In particular, the model produced **20 false negatives**.

The F1-score was **86.59%**, representing a balance between precision and recall.

Overall, the model performed very well in terms of accuracy and precision. However, the lower recall indicates that there is room for improvement in identifying all positive cases.

The use of a maximum depth of 3 also kept the Decision Tree relatively simple. This makes the model easier to interpret while helping to control its complexity.


## 9. Decision Tree Structure

The Decision Tree structure was displayed using the custom `print_tree()` function.

Each internal node represents a decision based on a feature and threshold. For example, a node may contain a rule such as:

```text
If Feature <= Threshold:
    Go to the left branch
Else:
    Go to the right branch
```

The process continues until a leaf node is reached, where the model produces a final class prediction.

The tree structure demonstrates how the model transforms the input features into a sequence of decisions that leads to the final classification.


## 10. Limitations

Although the Decision Tree achieved strong results, the implementation has some limitations.

### 10.1 Maximum Tree Depth

The tree was restricted to a maximum depth of **3**. This helps prevent excessive complexity, but a deeper tree could potentially capture additional patterns in the data.

### 10.2 Manual Implementation

The Decision Tree was implemented from scratch. While this provides a better understanding of the algorithm, it does not include all the optimizations and advanced functionality available in professional machine learning libraries.

### 10.3 Dataset Dependence

The performance of the model depends on the quality and characteristics of the dataset. Different datasets or different training and testing splits could produce different results.

### 10.4 False Negatives

The model produced **20 false negatives**. Since false negatives contribute to the lower recall of **78.02%**, improving the identification of positive cases could be an important area for future improvement.

---

## 11. Conclusion

This project successfully implemented a Decision Tree classification algorithm from scratch using Python.

The implementation demonstrated the main stages of Decision Tree classification, including calculating Gini Impurity, identifying the best feature and threshold for splitting, recursively constructing the tree, making predictions, and evaluating the model.

With a maximum depth of **3**, the model achieved:

* **97.80% Accuracy**
* **97.26% Precision**
* **78.02% Recall**
* **86.59% F1-Score**

The confusion matrix showed **907 true negatives, 2 false positives, 20 false negatives, and 71 true positives**.

The results demonstrate that the manually implemented Decision Tree performed strongly on the test dataset, particularly in terms of overall accuracy and precision. However, the lower recall indicates that some positive cases were missed.

Overall, the project provided practical insight into how Decision Trees work internally and demonstrated how a classification model can be built and evaluated without relying on a pre-built Decision Tree implementation.
