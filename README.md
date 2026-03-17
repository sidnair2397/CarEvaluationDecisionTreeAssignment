# Car Evaluation Dataset Analysis

## Project Overview
This project focuses on predicting the acceptability of a car based on a set of technical and financial attributes. The dataset, sourced from [Kaggle](https://www.kaggle.com/datasets/elikplim/car-evaluation-data-set), is a classic benchmark for classification algorithms.

## Dataset Features
The dataset consists of 1,728 instances, where each feature is categorical in nature.

| Feature | Description | Categories |
| :--- | :--- | :--- |
| **Buying Price** | The initial purchase cost of the vehicle | `vhigh`, `high`, `med`, `low` |
| **Maintenance Cost** | The ongoing cost of vehicle maintenance | `vhigh`, `high`, `med`, `low` |
| **Number of Doors** | Total number of doors | `2`, `3`, `4`, `5more` |
| **Capacity** | Maximum seating capacity (persons) | `2`, `4`, `more` |
| **Luggage Boot** | The size of the luggage storage area | `small`, `med`, `big` |
| **Safety** | Estimated safety level of the car | `low`, `med`, `high` |
| **Acceptability (Target)** | The final evaluation of the car | `unacc`, `acc`, `good`, `vgood` |

---

## Model Selection: Decision Trees
Given that both the predictors and the target variable are categorical, **Decision Trees** are an ideal choice for this classification task for the following reasons:

1.  **Handling Categorical Data:** Decision Trees naturally handle discrete features and do not require the complex normalization or scaling often needed for distance-based models.
2.  **Rule-Based Logic:** The evaluation of a car often follows a logical "if-then" structure (e.g., if safety is `low`, the car is automatically `unacc`). Decision Trees excel at capturing these non-linear relationships.
3.  **Interpretability:** The model provides a transparent decision-making process that can be easily visualized as a flowchart, making it highly explainable for stakeholders.

## Preprocessing Strategy
To prepare the data for modeling in Python (specifically with `scikit-learn`), we will utilize **Ordinal Encoding**. Since many of the features have an inherent rank (e.g., `low` < `med` < `high`), preserving this order will allow the Decision Tree to make more informed splits.
