# Evaluation Metrics

## Question

How can we properly evaluate a classification model when different types of
prediction errors have different implications?

## Core Idea

A classification model can make different types of correct and incorrect
predictions. Evaluation metrics quantify these outcomes from different
perspectives.

The main metrics explored here are:

- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC

A confusion matrix provides the underlying counts of true positives, true
negatives, false positives, and false negatives from which several of these
metrics are derived.

## Mathematics

### Accuracy

Measures the proportion of all predictions that are correct.

$$
Accuracy = \frac{TP + TN}{TP + TN + FP + FN}
$$

### Precision

Measures the proportion of positive predictions that are actually positive.

$$
Precision = \frac{TP}{TP + FP}
$$

### Recall

Measures the proportion of actual positive samples that are correctly
identified.

$$
Recall = \frac{TP}{TP + FN}
$$

### F1 Score

The harmonic mean of precision and recall.

$$
F1 = 2\frac{Precision \cdot Recall}
{Precision + Recall}
$$

### ROC-AUC

ROC-AUC measures how well a classifier distinguishes between the two classes
across different classification thresholds.

## Experiment

The notebook evaluates a Decision Tree classifier on the Breast Cancer
dataset using accuracy, precision, recall, F1 score, and ROC-AUC.

A confusion matrix is also plotted to examine the types of errors made by the
model.

The experiment then compares two trees with different levels of complexity:

- `max_depth = 5`
- `max_depth = 1`

The comparison demonstrates that accuracy alone can give an incomplete
picture of model performance. In particular, the shallower tree can maintain
apparently acceptable accuracy while its recall drops substantially.

## What I Learned

- How the confusion matrix forms the basis of classification evaluation.
- Why accuracy alone is not always sufficient for evaluating a model.
- How precision and recall measure different types of performance.
- How F1 balances precision and recall.
- How ROC-AUC evaluates class discrimination across thresholds.
- How model complexity can affect different evaluation metrics differently.
- Why the appropriate evaluation metric depends on what types of errors
  matter for the problem.

## Notebook

[Open the Evaluation Metrics notebook](./evaluation_metrics.ipynb)