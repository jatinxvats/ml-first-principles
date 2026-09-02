# Gradient Boosting

## Question

How can we combine multiple weak models sequentially so that each new model
corrects the errors made by the previous ones?

## Core Idea

Gradient boosting builds an ensemble of weak learners sequentially.

Instead of training all models independently, each new model is trained to
reduce the errors that remain after the existing ensemble. The predictions
from the new learner are then added to the current model, gradually improving
the overall prediction.

The key idea is that the ensemble is built by repeatedly moving in a direction
that reduces the loss function.

## Mathematics

The model is built iteratively:

$$
F_m(x) = F_{m-1}(x) + \eta h_m(x)
$$

where \(F_{m-1}(x)\) is the existing ensemble, \(h_m(x)\) is the new weak
learner, and \(\eta\) is the learning rate.

The new learner is chosen to approximate the negative gradient of the loss
with respect to the current predictions:

$$
r_{im} =
-\left[
\frac{\partial L(y_i,F(x_i))}
{\partial F(x_i)}
\right]_{F=F_{m-1}}
$$

Thus, each successive learner attempts to correct the direction in which the
current model is performing poorly.

## From-Scratch Implementation

The notebook works through the sequential construction of a gradient boosting
model and implements the underlying process from scratch.

The implementation demonstrates how weak learners are added iteratively and
how each learner contributes to improving the ensemble, while also exploring 
an edge case.

## What I Learned

- Why combining weak learners sequentially can produce a strong model.
- How gradient boosting differs from independently trained ensemble methods.
- How each new learner focuses on the errors of the current ensemble.
- How the negative gradient connects gradient boosting to optimization.
- How the learning rate controls the contribution of each new learner.
- Why the number of boosting iterations affects the model's complexity.

## Notebook

[Open the Gradient Boosting notebook](./gradient_boosting.ipynb)