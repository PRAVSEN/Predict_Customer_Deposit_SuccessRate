# Bank Marketing Campaign Analysis (`bank-additional-full` Dataset)

 

## Dataset Overview

 

This dataset, sourced from the UCI Machine Learning Repository, contains data from 17 distinct marketing campaigns conducted by a Portuguese bank. The objective is to predict whether a customer will subscribe to a term deposit (`y = yes`).

 

- Total records: 41,888

- Features: 21

- Missing values: None

- Target variable: `y` (binary classification: `yes` or `no`)

 

## Exploratory Data Analysis

 

- **Monthly Trends**:

  - The month of May shows an unusually high number of rejections (~12,000), which may indicate an outlier. However, confirmation would require historical data from previous years.

 

- **Correlation Insights**:

  - The features `duration` and `previous` exhibit a strong positive correlation with successful outcomes.

 

- **Categorical Feature Observations**:

  - Higher success rates were observed among:

    - Students

    - Individuals with no formal education or degree

    - Customers contacted via cellphone

    - Customers with positive outcomes in previous campaigns

 

## Model Engineering

 

### Class Imbalance

 

- The dataset is highly imbalanced:

  - Approximately 12% of customers subscribed (`y = yes`)

  - The majority class (`y = no`) dominates, which can lead to misleading accuracy metrics

 

### Baseline Model

 

- A dummy regressor was used with an 80/20 train-test split

- Accuracy: 88.65%

 

### Logistic Regression (Basic)

 

- Applied without hyperparameter tuning

- Accuracy remained at 88.65%, matching the baseline

 

### Model Comparisons

 

##  Model Performance Comparison

| Model                   | Train Accuracy | Test Accuracy | Notes                             |
|------------------------|----------------|----------------|-----------------------------------|
| Logistic Regression    | High           | High           | Consistent performance            |
| K-Nearest Neighbors    | High           | Lower          | Overfits training data            |
| Decision Tree          | Very High      | Lower          | Fast training, poor generalization |
| Support Vector Machine | High           | High           | Long training time, consistent    |


 

### Hyperparameter Tuning

 

- Various tuning attempts did not yield significant improvements

- The class imbalance remained a limiting factor

 

## Confusion Matrix and Balancing

 

- Confusion matrix analysis revealed a high number of false negatives for the minority class (`y = yes`)

- Class balancing techniques were applied:

  - Accuracy decreased slightly

  - Recall and F1-score improved, indicating better performance on the minority class

 

## Conclusion

 

- A model trained on the original dataset tends to predict `no` for most cases, achieving high accuracy but offering limited business value

- The minority class (`y = yes`) represents the true business objective: identifying potential subscribers

- Key metrics to prioritize:

  - **Recall**: Ensures more potential subscribers are identified

  - **Precision**: Reduces false positives and minimizes wasted effort

  - **F1-score**: Balances precision and recall for effective targeting

 

Sacrificing a small amount of accuracy to improve recall and F1-score leads to more effective marketing strategies, better targeting of potential customers, and higher conversion rates.
