# Linear Regression

## Question

How can we model the relationship between an input variable and a continuous
output using a straight line?

## Core Idea

Linear regression assumes that the target variable can be approximated as a
linear combination of the input features.

The model learns the parameters of this linear relationship by minimizing the
difference between the predicted and actual values.

## Mathematics

The model can be written as:

$$
\hat{y} = Xw + b
$$

The parameters are learned by minimizing a loss function based on the prediction
errors.

## From-Scratch Implementation

The algorithm is implemented from scratch in Python without using a
machine-learning library for the underlying optimization.

The implementation follows the mathematical derivation and uses gradient
descent to learn the model parameters.

## What I Learned

- How linear regression represents a relationship mathematically.
- How the loss function measures prediction error.
- How the gradient tells us how to update the model parameters.
- How gradient descent iteratively minimizes the loss.
- How the mathematical formulation translates into an actual implementation.

## Notebook

[Open the Linear Regression notebook](./linear_regression.ipynb)