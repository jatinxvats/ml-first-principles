# Optimization

## Question

Once a neural network has calculated the gradient of its loss, how can we use
that gradient to efficiently update the model's parameters and improve its
predictions?

## Core Idea

Optimization is the process of adjusting a neural network's parameters to
minimize its loss.

The optimizer uses the gradients calculated during backpropagation to determine
how the weights and biases should change.

In this notebook, Adam was explored as an optimization algorithm for training a
neural network.

## Adam

Adam (Adaptive Moment Estimation) combines ideas from momentum and adaptive
learning rates.

It maintains moving averages of the gradients and their squared values.

For gradient \(g_t\),

\[
m_t = \beta_1m_{t-1} + (1-\beta_1)g_t
\]

\[
v_t = \beta_2v_{t-1} + (1-\beta_2)g_t^2
\]

Because these estimates are initialized at zero, bias correction is applied:

\[
\hat{m}_t = \frac{m_t}{1-\beta_1^t}
\]

\[
\hat{v}_t = \frac{v_t}{1-\beta_2^t}
\]

The parameter update is then:

\[
\theta_t =
\theta_{t-1}
-
\eta
\frac{\hat{m}_t}{\sqrt{\hat{v}_t}+\epsilon}
\]

where:

- \(\theta\) represents the model parameters
- \(\eta\) is the learning rate
- \(m_t\) tracks the first moment of the gradients
- \(v_t\) tracks the second moment
- \(\beta_1\) and \(\beta_2\) control the moving averages
- \(\epsilon\) provides numerical stability

## Experiment

### XOR Dataset

Used the XOR dataset to train a neural network using Adam optimization.

XOR provides a useful test case because it requires a non-linear decision
boundary and therefore connects directly with the earlier experiments on
perceptrons, neural networks, activation functions, and backpropagation.

### Visualization

Plotted the optimization/training behavior to visualize how the model
progressed while learning the XOR problem.

This provided a direct view of the relationship between optimization and the
network's ability to reduce its error.

## What I Learned

- Optimization is the mechanism that turns gradients into parameter updates.
- Backpropagation calculates the gradients, while the optimizer determines how
  those gradients are used to update parameters.
- Adam maintains moving estimates of both the gradient and its squared value.
- Bias correction is required because these moving averages begin at zero.
- The XOR experiment connected optimization with the complete neural-network
  learning process.
- Visualizing training makes the optimization process easier to understand
  than looking only at the final predictions.

## Notebook

[Open the Optimization notebook](./optimization.ipynb)