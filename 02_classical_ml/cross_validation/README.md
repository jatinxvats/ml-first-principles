# Cross-Validation

## Question

How can we obtain a more reliable estimate of a model's performance without
relying on a single train-validation split?

## Core Idea

Cross-validation evaluates a model across multiple different partitions of
the dataset.

In k-fold cross-validation, the data is divided into \(k\) folds. Each fold is
used once as the validation set while the remaining \(k-1\) folds are used for
training.

This produces \(k\) validation scores, which can then be summarized using
their mean and standard deviation.

## Mathematics

For \(k\) validation scores \(s_1, s_2, \ldots, s_k\), the mean score is:

$$
\bar{s} = \frac{1}{k}\sum_{i=1}^{k}s_i
$$

The standard deviation describes how much the model's performance varies
across the different folds.

## From-Scratch Implementation

The notebook implements k-fold cross-validation from scratch using NumPy.

The implementation:

1. Creates and optionally shuffles the sample indices.
2. Divides the indices into \(k\) folds.
3. Uses one fold for validation and the remaining folds for training.
4. Trains and evaluates the model for each fold.
5. Collects the resulting scores.
6. Calculates the mean and standard deviation.

The implementation is then verified against
`sklearn.model_selection.cross_val_score`.

## What I Learned

- How k-fold cross-validation works internally.
- Why evaluating a model on multiple validation folds provides a more
  reliable estimate of performance.
- How fold-by-fold scores reveal variation in model performance.
- How the mean summarizes performance across folds.
- How the standard deviation indicates the stability of the model's
  performance across different splits.
- How implementing an established method from scratch can be verified
  against a library implementation.

## Notebook

[Open the Cross-Validation notebook](./cross_validation.ipynb)