# LendingClub

## Project Overview
The project consisted of determining the total number of employees per title who will be retiring and identifying the employees who are eligible to participate in a mentorship program.

## Resources
- Data source:
    - LoanStats_2019Q1.csv
- Software: Python 3.7.7, Jupyter Notebook, Visual Studio Code 1.43.1

## Preprocessing:
* Drop features that contain the same value throughout all rows


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

- **Oversampling Algorithms:**
    - Naive Random Oversampling
    | Model | Loan Status | Accuracy | Precision | Recall | F1 Score |
    | ------ | ------ | ------ | ------ | ------ | ------ |
    | Naive Random Oversampling | high_risk | 0.78 | 0.02 | 0.70 | 0.05 |
    | Naive Random Oversampling | low_risk | 0.78 | 1.00 | 0.86 | 0.92 |  
    - SMOTE Oversampling
    Model | Loan Status | Accuracy | Precision | Recall | F1 Score
    ------ | ------ | ------ | ------ | ------ | ------
    SMOTE | high_risk | 0.80 | 0.03 | 0.70 | 0.06
    SMOTE | low_risk | 0.80 | 1.00 | 0.88 | 0.94 
- **Undersampling Algorithm:**
    - Cluster Centroids
- **Combination Over and Undersampling Algorithm:**
    - SMOTEENN
- **Ensemble Algorithms:**
    - Balanced Random Forest Classifier
    - Easy Ensemble AdaBoost Classifier

Model | Loan Status | Accuracy | Precision | Recall | F1 Score
------ | ------ | ------ | ------ | ------ | ------
Naive Random Oversampling | high_risk | 0.78 | 0.02 | 0.70 | 0.05
Naive Random Oversampling | low_risk | 0.78 | 1.00 | 0.86 | 0.92
SMOTE | high_risk | 0.80 | 0.03 | 0.70 | 0.06
SMOTE | low_risk | 0.80 | 1.00 | 0.88 | 0.94
Undersampling | high_risk | 0.78 | 0.02 | 0.78 | 0.03
Undersampling | low_risk | 0.78 | 1.00 | 0.77 | 0.87
SMOTEENN | high_risk | 0.50 | 0.01 | 0.99 | 0.03
SMOTEENN | low_risk | 0.50 | 0.99 | 0.01 | 0.02
Balanced Random Forest | high_risk | 0.77 | 0.04 | 0.64 | 0.07
Balanced Random Forest | low_risk | 0.77 | 1.00 | 0.90 | 0.95
Easy Ensemble AdaBoost | high_risk | 0.91 | 0.06 | 0.92 | 0.12
Easy Ensemble AdaBoost | low_risk | 0.91 | 1.00 | 0.92 | 0.96

The over and undersampling models had relatively high accuracy (78-79%). However, despite the high precision for the majority class (low_risk), meaning a reliable positive classification, the precision for high_risk loan statuses was very low, indicating a large number of false positives (most that were considered to be high_risk were actually low_risk).

The sensitivity (recall) for the majority class (low_risk) was lower for the Oversampling models, meaning a large number of false negatives; and about the same for the Undersampling one.

Using the SMOTEENN model, the accuracy was much reduced, and the sensitivity was very high for detecting high_risk loans, which would be important for predicting credit risk. However, like with the previous models, the precision was extremely low, resulting in very low F1 scores and many false positives.

The Balanced Random Forest Classifier model had a similar performance to the Over and Undersampling ones.

In summary, this model may not be the best one for preventing fraudulent loan applications because the model's accuracy, 0.552, is low, and the precision and recall are not good enough to state that the model will be good at classifying fraudulent loan applications. Modeling is an iterative process: you may need more data, more cleaning, another model parameter, or a different model. It’s also important to have a goal that’s been agreed upon, so that you know when the model is good enough.

From the confusion matrix results, the precision for the bad loan applications is low, indicating a large number of false positives, which indicates an unreliable positive classification. The recall is also low for the bad loan applications, which is indicative of a large number of false negatives. The F1 score is also low (33).

In summary, this random forest model is not good at classifying fraudulent loan applications because the model’s accuracy, 0.520, and F1 score are low.
