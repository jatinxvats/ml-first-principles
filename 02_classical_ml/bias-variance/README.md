# Bias–Variance Tradeoff

## Question

Why can increasing a model's complexity improve its performance at first, but
eventually make it generalize worse?

## Core Idea

The bias–variance tradeoff describes the relationship between model
complexity and two sources of prediction error.

**Bias** is the error introduced when a model is too simple to capture the
underlying relationship in the data.

**Variance** measures how much a model's predictions change when it is trained
on different samples of the data.

As model complexity increases, bias generally decreases while variance
increases. The goal is to find a balance between the two.

## Mathematics

Expected prediction error can be decomposed into three components:

$$
\text{Total Error}
=
\text{Bias}^2
+
\text{Variance}
+
\text{Irreducible Noise}
$$

In this experiment, the underlying function is known, allowing bias and
variance to be measured directly.

## From Scratch Implementation

The notebook demonstrates the bias–variance tradeoff empirically using
`DecisionTreeRegressor` on a noisy sine-wave dataset.

Multiple training datasets are generated, and decision trees with different
maximum depths are trained on these datasets.

For each tree depth, the experiment calculates:

- Bias²
- Variance
- Total prediction error

The resulting curves show how increasing tree complexity reduces bias while
increasing variance.

The total error follows the characteristic **U-shaped curve**, demonstrating
that both an overly simple and an overly complex model can perform poorly.

## What I Learned

- How model complexity affects bias and variance.
- Why shallow decision trees tend to have higher bias.
- Why deeper decision trees tend to have higher variance.
- How the bias–variance tradeoff can be observed experimentally.
- Why the model with the lowest training error is not necessarily the model
  with the best generalization.
- How the U-shaped total error curve emerges from the interaction between
  bias and variance.

## Notebook

[Open the Bias–Variance notebook](./bias_variance.ipynb)