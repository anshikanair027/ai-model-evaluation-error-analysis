
# AI Model Evaluation & Error Analysis

## 1. Project Overview

This project evaluates a Logistic Regression classification model using the Wisconsin Breast Cancer Diagnostic dataset.

The objective is to assess how effectively a machine learning model distinguishes between benign and malignant cases, identify prediction errors, and understand its performance across different feature-based groups.

The project focuses on model evaluation beyond overall accuracy, with particular attention to precision, recall, false positives, false negatives, and model reliability.

This is a benchmark analysis for educational purposes and is not intended for clinical diagnosis.

## 2. Dataset Source

**Dataset:** Wisconsin Breast Cancer Diagnostic Dataset

**Source:** [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/17/breast+cancer+wisconsin+diagnostic)

The dataset was accessed using Scikit-learn's built-in `load_breast_cancer()` function.

Dataset characteristics:
- 569 observations.
- 30 numerical predictor features.
- Two classification categories: Benign and Malignant.

The features represent measurements extracted from digitised images of breast masses.

## 3. Model and Evaluation Approach

### Data Preparation
- Inspected dataset structure, data types and statistical summaries.
- Checked missing values, duplicate records and invalid values.
- Verified and encoded target labels.
- Split the dataset into training (80%) and testing (20%) sets.
- Applied feature standardisation using `StandardScaler`.

### Model Development

A Logistic Regression classification model was developed using Scikit-learn.

The model was configured with:
- Algorithm: Logistic Regression
- Feature scaling: StandardScaler
- Training/testing split: 80:20
- Random state: 42
- Positive class: Malignant

### Error Analysis

The evaluation included:
- Confusion matrix analysis.
- Identification of false positives and false negatives.
- Examination of individual prediction outcomes.
- Comparison of model performance across four mean-radius feature groups.

## 4. Evaluation Metrics

The following metrics were used to evaluate model performance:

| Metric | Result |
|---|---:|
| Accuracy | 96.49% |
| Precision | 97.50% |
| Recall | 92.86% |
| F1-score | 95.12% |
| ROC-AUC | 99.60% |

### Metric Interpretation

- **Accuracy:** 96.49% of test observations were classified correctly.
- **Precision:** 97.50% of predicted malignant cases were actually malignant.
- **Recall:** 92.86% of actual malignant cases were correctly identified.
- **F1-score:** 95.12%, representing the balance between precision and recall.
- **ROC-AUC:** 99.60%, indicating strong discrimination between the two classes on this test split.

## 5. Error Analysis and Key Findings

The model was evaluated on 114 test observations.

| Prediction Outcome | Count |
|---|---:|
| Correct Predictions | 110 |
| False Positives | 1 |
| False Negatives | 3 |
| Total | 114 |

### Key Observations

1. The model correctly classified 110 out of 114 test observations.
2. One false positive was recorded, where a benign observation was predicted as malignant.
3. Three false negatives were recorded, where actual malignant observations were predicted as benign.
4. The recall score of 92.86% indicates that some malignant observations were not identified by the model.
5. The high ROC-AUC score indicates strong class discrimination on the selected test dataset.

### Subgroup Performance Analysis

The model was also evaluated across four groups based on the `mean radius` feature.

| Mean Radius Group | Observations | Accuracy |
|---|---:|---:|
| 7.759–11.608 | 29 | 100.00% |
| 11.608–13.430 | 28 | 96.43% |
| 13.430–15.302 | 28 | 89.29% |
| 15.302–23.090 | 29 | 100.00% |

The third group recorded the lowest accuracy at 89.29%, while the first and fourth groups recorded 100% accuracy.

These comparisons are exploratory. The first group contained no actual malignant observations, so its recall and precision should not be interpreted as evidence of perfect malignant-case detection.

## 6. Limitations

- The analysis uses a relatively small benchmark dataset.
- Results depend on the selected training and testing split.
- Logistic Regression may not capture all complex relationships in the data.
- Subgroup analysis is exploratory and may be affected by small sample sizes.
- The evaluation does not establish causal relationships.
- The model is intended for educational evaluation and is not suitable for clinical use.

## 7. Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn
- Google Colab

## 8. Project Outputs

The repository includes the following generated outputs:

| File | Description |
|---|---|
| `evaluation_metrics.csv` | Model evaluation scores |
| `prediction_results.csv` | Actual labels, predicted labels and prediction probabilities |
| `error_summary.csv` | Counts of correct predictions, false positives and false negatives |
| `subgroup_performance.csv` | Evaluation metrics across feature-based groups |
| `model_evaluation_report.md` | Detailed model evaluation report |

## 9. How to Run the Notebook

1. Clone or download this GitHub repository.
2. Open `AI_Model_Evaluation_Error_Analysis.ipynb` in Google Colab.
3. Ensure the required Python libraries are available.
4. Execute the notebook cells sequentially.
5. Review the evaluation metrics, confusion matrix, prediction errors and subgroup comparisons.
6. Refer to the `outputs/` directory for the generated evaluation results.

## 10. Conclusion

This project demonstrates the application of machine learning evaluation techniques to assess classification performance and investigate prediction errors.

The Logistic Regression model achieved 96.49% accuracy and a 95.12% F1-score on the held-out test dataset. However, the identification of three false negatives highlights why evaluating individual error types is important beyond overall accuracy.

The project provides practical experience in classification, model evaluation, error analysis and interpreting machine learning performance.

---

**Project Status:** Completed
