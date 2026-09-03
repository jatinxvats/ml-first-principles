# Loss Functions

## Question

How does a neural network measure how wrong its predictions are, and how does
the choice of loss function affect the way it learns?

## Core Idea

A loss function measures the discrepancy between a model's prediction and the
true target.

During training, the network uses the loss to determine how its parameters
should be updated through backpropagation and optimization.

Different loss functions respond differently to errors, making some more
sensitive to outliers and others more appropriate for classification.

## Mathematics

### Mean Squared Error (MSE)

\[
L_{MSE} = \frac{1}{n}\sum_{i=1}^{n}(y_i-\hat{y}_i)^2
\]

MSE squares the error, causing larger errors to contribute disproportionately
to the total loss.

### Mean Absolute Error (MAE)

\[
L_{MAE} = \frac{1}{n}\sum_{i=1}^{n}|y_i-\hat{y}_i|
\]

MAE measures the absolute difference between the prediction and target.

Compared with MSE, it is less sensitive to large errors and outliers.

### Huber Loss

Huber loss combines the behavior of MSE for small errors with MAE-like
behavior for large errors.

\[
L_\delta(a)=
\begin{cases}
\frac{1}{2}a^2 & |a|\leq\delta\\
\delta\left(|a|-\frac{1}{2}\delta\right) & |a|>\delta
\end{cases}
\]

where

\[
a = y-\hat{y}
\]

The parameter \(\delta\) determines the point at which the loss transitions
from quadratic to linear behavior.

## Softmax

Softmax converts a vector of logits into a probability distribution.

\[
\text{softmax}(z_i)=
\frac{e^{z_i}}{\sum_{j=1}^{K}e^{z_j}}
\]

The resulting values lie between 0 and 1 and sum to 1.

Softmax is commonly used at the output of a multi-class classification
network before applying categorical cross-entropy.

## Categorical Cross-Entropy

For a multi-class classification problem,

\[
L = -\sum_{i=1}^{K} y_i\log(\hat{y}_i)
\]

where \(y_i\) represents the true class distribution and \(\hat{y}_i\)
represents the predicted probability distribution.

For a one-hot encoded target, only the probability assigned to the correct
class contributes to the loss.

The loss therefore strongly penalizes confident predictions that assign a
small probability to the correct class.

## From-Scratch Implementation

Implemented and explored the following from scratch:

- Mean Squared Error (MSE)
- Mean Absolute Error (MAE)
- Huber Loss
- Softmax
- Categorical Cross-Entropy

The implementations were used to understand how each function transforms
prediction errors into a quantity that can guide learning.

## What I Learned

- A loss function provides the numerical signal that tells the network how
  wrong its prediction is.
- MSE penalizes large errors more strongly because the error is squared.
- MAE grows linearly with the magnitude of the error.
- Huber loss combines quadratic behavior for small errors with linear behavior
  for large errors.
- Softmax converts logits into a probability distribution for multi-class
  classification.
- Categorical cross-entropy measures the difference between the true class
  distribution and the predicted distribution.
- The choice of loss function changes the optimization landscape and therefore
  affects how a model learns.

## Notebook

[Open the Loss Functions notebook](./loss_functions.ipynb)