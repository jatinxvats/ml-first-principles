# Logistic Regression — From First Principles

## Question

How can we use a mathematical model to predict the probability of a binary
outcome?

## Core Idea

Logistic regression models the probability of a binary outcome by passing a
linear combination of the input features through the sigmoid function.

The sigmoid maps any real-valued input to a value between 0 and 1, allowing the
model output to be interpreted as a probability.

A classification decision can then be made by applying a threshold to this
probability.

## Mathematics

The model first computes a linear combination of the input features:

$$
z = Xw + b
$$

This value is passed through the sigmoid function:

$$
\sigma(z) = \frac{1}{1 + e^{-z}}
$$

The resulting value represents the predicted probability of the positive
class.

The model parameters are learned by minimizing a loss function based on the
predicted probabilities and the true labels.

## From-Scratch Implementation

The algorithm is implemented from scratch in Python by deriving the
mathematical operations behind logistic regression and translating them into
code.

The implementation includes the sigmoid function, loss calculation, gradient
calculation, and parameter updates using gradient descent.

## What I Learned

- Why linear regression is not directly suitable for binary classification.
- How the sigmoid function converts a linear output into a
  probability.
- How logistic regression learns its parameters through gradient descent.
- How the loss function guides the parameter updates.
- How predicted probabilities are converted into class predictions using a
  decision threshold.
- How the mathematical formulation translates into a from-scratch
  implementation.

## Notebook

[Open the Logistic Regression notebook](./logistic_regression.ipynb)