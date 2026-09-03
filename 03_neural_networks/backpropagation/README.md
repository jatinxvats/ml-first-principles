# Backpropagation

## Question

How can a neural network determine how much each weight and bias contributed
to its final error, and use that information to improve itself?

## Core Idea

Backpropagation is the algorithm used to efficiently calculate the gradients
of a neural network's loss with respect to its parameters.

The key idea is to apply the chain rule of calculus backwards through the
network.

Starting from the loss at the output, the gradients are propagated backwards
through each layer. These gradients tell us how changes in the weights and
biases would affect the loss.

The resulting gradients can then be used by an optimization algorithm such
as gradient descent to update the parameters.

## Mathematics

For a parameter \(w\), the parameter update is determined by its gradient:

$$
w \leftarrow w - \eta \frac{\partial L}{\partial w}
$$

For a multi-layer network, the chain rule allows the derivative of the loss
with respect to an earlier parameter to be expressed as a product of
derivatives through the subsequent computations:

$$
\frac{\partial L}{\partial w}
=
\frac{\partial L}{\partial a}
\frac{\partial a}{\partial z}
\frac{\partial z}{\partial w}
$$

By repeatedly applying the chain rule from the output layer backwards,
gradients for all the network's parameters can be calculated efficiently.

## Mathematical Derivation

A complete five-page derivation of backpropagation was worked through from
first principles, using the chain rule to derive the gradients through the
network.

[View the complete derivation](./backpropagation_derivation.pdf)

## From-Scratch Implementation

The notebook derives and implements backpropagation from scratch.

The derivation follows the flow of information through the network and works
backwards from the loss to determine the gradients of the parameters.

The resulting gradients are then used to update the network's weights and
biases.

## Experiment

The implementation is tested on the **XOR dataset**.

XOR is particularly useful here because a single perceptron cannot solve it,
while a multi-layer neural network with non-linear activation functions can.

The experiment therefore demonstrates not only how backpropagation allows the
network to learn, but also how it enables the multi-layer architecture
introduced in the previous neural network experiment to solve a problem that
the perceptron could not.

## What I Learned

- How the chain rule allows gradients to be propagated backwards through a
  neural network.
- How each parameter's contribution to the final loss can be determined.
- Why backpropagation is fundamentally an application of calculus and the
  chain rule.
- How the calculated gradients are used to update network parameters.
- How a multi-layer network can learn the XOR function using backpropagation.
- How backpropagation connects the mathematical structure of a neural network
  with its ability to learn.

## Notebook

[Open the Backpropagation notebook](./backpropagation.ipynb)