# Regularization

## Question

How can regularization reduce overfitting and improve a model's ability to
generalize to unseen data?

## Core Idea

Regularization adds a penalty for model complexity during training.

Instead of minimizing only the original loss, the model minimizes a combined
objective that also penalizes large parameter values.

This discourages the model from relying too heavily on individual features or
learning overly complex patterns from the training data.

## Mathematics

### L2 Regularization

L2 regularization adds a penalty proportional to the squared magnitude of the
model parameters:

\[
L_{regularized}
=
L_{original}
+
\lambda \sum_j w_j^2
\]

where \(\lambda\) controls the strength of the regularization.

### L1 Regularization

L1 regularization instead penalizes the absolute magnitude of the parameters:

\[
L_{regularized}
=
L_{original}
+
\lambda \sum_j |w_j|
\]

L1 regularization can encourage some parameters to become exactly zero,
effectively performing feature selection.

## Experiment

Used scikit-learn to study the effect of regularization by examining model
behavior separately on the training and test data.

The comparison focused on how regularization affects:

- Training performance
- Test performance
- The gap between training and test performance
- Generalization to unseen data

Separating the training and test evaluations made it possible to distinguish
memorization of the training data from actual generalization.

## What I Learned

- A model can perform very well on training data while performing worse on
  unseen data.
- Regularization controls model complexity and can reduce overfitting.
- Training performance alone is not sufficient to determine whether a model
  generalizes well.
- Comparing training and test performance provides a clearer picture of
  overfitting and generalization.
- Regularization introduces a trade-off between fitting the training data and
  keeping the model sufficiently simple.

## Implementation

Regularization was implemented from scratch and than compared with the results
from scikit-learn.

## Notebook

[Open the Regularization notebook](./regularization.ipynb)