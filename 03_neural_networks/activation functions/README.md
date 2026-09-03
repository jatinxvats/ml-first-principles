# Activation Functions

## Question

Why do neural networks need activation functions, and how does the choice of
activation function affect learning and gradient flow?

## Core Idea

Activation functions introduce non-linearity into neural networks.

Without non-linear activation functions, stacking multiple layers would still
produce a linear transformation, limiting the kinds of patterns the network
could learn.

The activation function also determines how gradients behave during
backpropagation, making its derivative an important part of neural network
training.

## Mathematics

For a neuron,

\[
z = w^T x + b
\]

and the activation is

\[
a = f(z)
\]

### Sigmoid

\[
\sigma(z) = \frac{1}{1 + e^{-z}}
\]

Its derivative is

\[
\sigma'(z) = \sigma(z)(1-\sigma(z))
\]

Sigmoid maps inputs to the range \((0,1)\).

### ReLU

\[
\text{ReLU}(z) = \max(0,z)
\]

Its derivative is

\[
\text{ReLU}'(z) =
\begin{cases}
0 & z < 0 \\
1 & z > 0
\end{cases}
\]

### Leaky ReLU

\[
\text{LeakyReLU}(z) =
\begin{cases}
z & z > 0 \\
\alpha z & z \leq 0
\end{cases}
\]

Its derivative is

\[
\text{LeakyReLU}'(z) =
\begin{cases}
1 & z > 0 \\
\alpha & z \leq 0
\end{cases}
\]

where \(\alpha\) is a small positive constant.

## From-Scratch Implementation

Implemented the activation functions and their derivatives from scratch,
without relying on neural-network libraries for the underlying calculations.

The implementations covered:

- Sigmoid
- ReLU
- Leaky ReLU
- Derivatives of all three functions

## Visualization

Plotted the activation functions and their corresponding derivatives to
observe how their outputs and gradients change across different input values.

The plots make the differences in their shapes, output ranges, and gradient
behavior directly visible.

## Experiment

### XOR Dataset

Tested activation functions within a neural network on the XOR dataset.

The experiment connected the role of non-linearity to the earlier study of the
perceptron: XOR cannot be solved by a single linear decision boundary, but a
multi-layer network with non-linear activations can represent the required
decision boundary.

### ReLU Network — Repeated Attempts

Ran the ReLU-based network for ten separate attempts to observe variation in
the training outcome rather than relying on a single run.

This helped examine how neural-network training can produce different outcomes
across runs.

## What I Learned

- Activation functions introduce the non-linearity that allows neural networks
  to learn non-linear relationships.
- The derivative of an activation function directly affects backpropagation.
- Sigmoid, ReLU, and Leaky ReLU have fundamentally different gradient
  behaviors.
- ReLU provides a simple piecewise-linear transformation.
- Leaky ReLU preserves a small gradient for negative inputs.
- The XOR experiment demonstrates why non-linear activations are necessary
  for solving problems that cannot be represented by a single linear
  decision boundary.
- Repeating the same neural-network experiment can produce different training
  outcomes.

## Notebook

[Open the Activation Functions notebook](./activation_functions.ipynb)