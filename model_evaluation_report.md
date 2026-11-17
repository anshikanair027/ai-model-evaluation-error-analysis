
# AI Model Evaluation & Error Analysis

## Project Overview

This project evaluates a Logistic Regression classification model
using the Wisconsin Breast Cancer Diagnostic dataset.

The model predicts whether an observation is malignant or benign.
This is a benchmark analysis and not a medical diagnostic tool.

## Model

- Algorithm: Logistic Regression
- Feature scaling: StandardScaler
- Train-test split: 80% training, 20% testing
- Random state: 42
- Positive class: Malignant

## Evaluation Metrics

- Accuracy: 0.9649
- Precision: 0.9750
- Recall: 0.9286
- F1 Score: 0.9512
- ROC-AUC: 0.9960

## Error Analysis

- False Positives: 1
- False Negatives: 3

A false negative represents an actual malignant observation
that the model predicted as benign.

A false positive represents an actual benign observation
that the model predicted as malignant.

## Interpretation

The metrics describe the model's performance on the held-out
test dataset. Recall measures the proportion of actual malignant
observations detected by the model.

The confusion matrix and error tables should be examined to
understand the types of mistakes made by the classifier.

## Limitations

- This is a small benchmark dataset.
- Results depend on the selected train-test split.
- The model is not intended for clinical use.
- Subgroup analysis is exploratory.
- The model does not establish causal relationships.

## Conclusion

The project demonstrates model evaluation, classification
metrics, error analysis, and subgroup performance comparison
using Python and scikit-learn.
