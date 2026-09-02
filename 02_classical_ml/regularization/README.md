# Regularization

## Question

How can we prevent a machine learning model from fitting the training data
too closely and improve its ability to generalize?

## Core Idea

Regularization reduces model complexity by adding a penalty to the loss
function when the model parameters become too large.

Instead of optimizing only for how well the model fits the training data,
regularized learning balances the fit against the complexity of the model.

Two common forms of regularization are L1 and L2 regularization.

## Mathematics

L1 regularization adds a penalty proportional to the absolute values of the
model parameters:

$$
J_{\text{L1}} = J + \lambda \sum_j |w_j|
$$

L2 regularization adds a penalty proportional to the squared values of the
parameters:

$$
J_{\text{L2}} = J + \lambda \sum_j w_j^2
$$

where \(\lambda\) controls the strength of the regularization.

A larger value of \(\lambda\) places greater emphasis on keeping the model
parameters small.

## From-Scratch Implementation

The notebook derives the effect of regularization on the optimization
objective and implements the corresponding parameter updates from scratch.

The implementation explores both L1 and L2 regularization and examines how
the regularization term changes the learning process.

## What I Learned

- Why minimizing training error alone can lead to overly complex models.
- How regularization incorporates model complexity into the optimization
  objective.
- How L1 and L2 regularization penalize model parameters differently.
- How the regularization strength \(\lambda\) controls the trade-off between
  fitting the data and constraining the model.
- How regularization connects optimization with the bias-variance trade-off.

## Notebook

[Open the Regularization notebook](./regularization.ipynb)