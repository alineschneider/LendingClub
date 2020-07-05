# LendingClub

## Project Overview
The project consisted of evaluating different models with unbalanced classes, including using resampling techniques, to determine whether they should be used to predict credit risk.

## Resources
- Data source:
    - LoanStats_2019Q1.csv
- Software: Python 3.7.7, Jupyter Notebook, Visual Studio Code 1.43.1

## Preprocessing:
* Dropped features that contain a single value throughout all rows, since they would not be useful for the model;
* Binary encoded categorical features;
* Standardized the data using Standard Scaler.

## Models Evaluated:
- **Oversampling Algorithms:**
    - Naive Random Oversampling
    - SMOTE Oversampling
- **Undersampling Algorithm:**
    - Cluster Centroids
- **Combination Over and Undersampling Algorithm:**
    - SMOTEENN
- **Ensemble Algorithms:**
    - Balanced Random Forest Classifier
    - Easy Ensemble AdaBoost Classifier

## Results
- **Naive Random Oversampling** (Accuracy = 0.78):

| Loan Status | Precision | Recall | F1 Score |
| ------ | ------ | ------ | ------ |
| high_risk | 0.02 | 0.70 | 0.05 |
| low_risk | 1.00 | 0.86 | 0.92 |

- **SMOTE Oversampling** (Accuracy = 0.80):

| Loan Status | Precision | Recall | F1 Score |
| ------ | ------ | ------ | ------ |
| high_risk | 0.03 | 0.71 | 0.06 |
| low_risk | 1.00 | 0.88 | 0.94 |

- **Cluster Centroids Undersampling** (Accuracy = 0.78):

| Loan Status | Precision | Recall | F1 Score |
| ------ | ------ | ------ | ------ |
| high_risk | 0.02 | 0.78 | 0.03 |
| low_risk | 1.00 | 0.77 | 0.87 |

- **SMOTEENN** (Accuracy = 0.50):

| Loan Status | Precision | Recall | F1 Score |
| ------ | ------ | ------ | ------ |
| high_risk | 0.01 | 0.99 | 0.01 |
| low_risk | 0.99 | 0.01 | 0.02 |

- **Balanced Random Forest** (Accuracy = 0.77):

| Loan Status | Precision | Recall | F1 Score |
| ------ | ------ | ------ | ------ |
| high_risk | 0.04 | 0.64 | 0.07 |
| low_risk | 1.00 | 0.90 | 0.95 |

- **Easy Ensemble AdaBoost** (Accuracy = 0.92):

| Loan Status | Precision | Recall | F1 Score |
| ------ | ------ | ------ | ------ |
| high_risk | 0.06 | 0.92 | 0.12 |
| low_risk | 0.91 | 0.92 | 0.96 |

For all methods analyzed, the Precision was very high for the majority class (low_risk), but very low for detecting high risk loans, indicating a large number of false positives (most that were considered to be high_risk were actually low_risk).

The Sensitivity (recall) for detecting high risk was lower for the two Oversampling models, but lowest using the Balanced Random Forest model. This measure would be a priority for predicting credit risk, since it's preferrable for the model to be aggressive in classifying loans as high risk than to have too many false negatives.

The model built using Easy Ensemble AdaBoost would be the best of the ones evaluated, since it has high accuracy, high Sensitivity for high_risk without sacrificing Sensitivity or Precision for low_risk detection. However, none of the models would be the great detecting high risk loan applications, considering the really low F1 scores for that class.
