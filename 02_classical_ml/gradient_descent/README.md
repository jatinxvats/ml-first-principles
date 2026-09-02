# Gradient Descent

## Question

How can we systematically find the parameters of a model that minimizes a
given loss function?

## Core Idea

Gradient descent is an iterative optimization algorithm used to minimize a
function.

Instead of directly solving for the parameters that minimize the loss, we
start with an initial set of parameters and repeatedly move them in the
direction that decreases the loss most rapidly.

The direction of steepest increase is given by the gradient, so moving in the
opposite direction allows us to minimize the function.

## Mathematics

For a parameter \(w\) and loss function \(J(w)\), the parameter is updated
according to:

$$
w := w - \alpha \frac{\partial J}{\partial w}
$$

where \(\alpha\) is the learning rate.

For multiple parameters, the update becomes:

$$
\mathbf{w} := \mathbf{w} - \alpha \nabla J(\mathbf{w})
$$

The learning rate determines the size of each step during optimization.

## From-Scratch Implementation

The notebook implements gradient descent from scratch and follows the
mathematical formulation directly.

The implementation initializes parameters, calculates the gradient of the
loss, updates the parameters, and repeats this process over multiple
iterations.

## What I Learned

- Why the gradient provides the direction of steepest increase of a function.
- Why moving opposite to the gradient minimizes the loss.
- How the learning rate controls the size of each optimization step.
- How gradient descent iteratively approaches a minimum.
- How the mathematical update rule translates directly into an
  implementation.
- Why choosing an appropriate learning rate is important for convergence.

## Notebook

[Open the Gradient Descent notebook](./gradient_descent.ipynb)