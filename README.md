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
### Oversampling Algorithms:
* Naive Random Oversampling
* SMOTE Oversampling
### Undersampling Algorithm:
* Cluster Centroids
### Combination Over and Undersampling Algorithm 
* SMOTEENN
### Ensemble Algorithms:
* Balanced Random Forest Classifier
* Easy Ensemble AdaBoost Classifier

## Results
Model | Loan Status | Accuracy | Precision | Recall | F1 Score
Naive Random Oversampling | high_risk | 0.78 | 0.02 | 0.70 | 0.05
Naive Random Oversampling | low_risk | 0.78 | 1.00 | 0.86 | 0.92
SMOTE | high_risk | 0.79 | 0.03 | 0.70 | 0.06
SMOTE | low_risk | 0.79 | 1.00 | 0.88 | 0.94


In summary, this model may not be the best one for preventing fraudulent loan applications because the model's accuracy, 0.552, is low, and the precision and recall are not good enough to state that the model will be good at classifying fraudulent loan applications. Modeling is an iterative process: you may need more data, more cleaning, another model parameter, or a different model. It’s also important to have a goal that’s been agreed upon, so that you know when the model is good enough.

From the confusion matrix results, the precision for the bad loan applications is low, indicating a large number of false positives, which indicates an unreliable positive classification. The recall is also low for the bad loan applications, which is indicative of a large number of false negatives. The F1 score is also low (33).

In summary, this random forest model is not good at classifying fraudulent loan applications because the model’s accuracy, 0.520, and F1 score are low.
