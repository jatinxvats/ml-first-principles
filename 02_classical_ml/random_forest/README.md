# Random Forest

## Question

How can we combine many decision trees to produce a model that is more
robust and generalizes better than an individual tree?

## Core Idea

A random forest is an ensemble of decision trees.

Instead of relying on a single tree, the algorithm trains many trees using
different samples of the training data and introduces randomness in the
features considered when making splits.

The predictions of the individual trees are then combined to produce the
final prediction.

This reduces the dependence on any single tree and helps control the
variance of the overall model.

## Mathematics

For classification, each tree produces a class prediction. The random forest
combines the predictions through majority voting:

$$
\hat{y} = \operatorname{mode}\{T_1(x), T_2(x), \ldots, T_B(x)\}
$$

where \(T_b(x)\) is the prediction of the \(b\)-th decision tree and \(B\) is
the total number of trees.

In this implementation, the forest consists of **100 decision trees**.

## From-Scratch Implementation

The notebook builds a random forest from the underlying ideas of ensemble
learning and decision trees.

It demonstrates how multiple decision trees can be trained with randomness
introduced into the learning process and how their predictions are combined
to produce the final result.

It is then compared to the results from Scikit-Learn.

## What I Learned

- Why a single decision tree can have high variance.
- How random forests reduce dependence on individual trees by combining
  multiple models.
- How randomness in the training samples and feature selection creates
  diverse trees.
- How majority voting produces the final classification.
- Why increasing the number of trees can make the ensemble more stable.
- How random forests connect the ideas of decision trees, variance
  reduction, and ensemble learning.

## Notebook

[Open the Random Forest notebook](./random_forest.ipynb)