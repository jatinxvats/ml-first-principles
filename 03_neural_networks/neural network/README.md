# Neural Network

## Question

How can multiple perceptrons be combined with non-linear transformations to
learn complex patterns that a single perceptron cannot represent?

## Core Idea

A neural network is built by arranging layers of interconnected neurons.

Each neuron computes a weighted sum of its inputs and applies an activation
function. By stacking multiple layers, the network can learn increasingly
complex transformations of the input data.

The introduction of non-linear activation functions allows neural networks
to represent non-linear relationships that a single perceptron cannot
capture.

## Mathematics

A neuron computes a weighted sum followed by an activation function:

$$
z = w^T x + b
$$

$$
a = f(z)
$$

For a layer of neurons, this can be written as:

$$
Z = XW + b
$$

$$
A = f(Z)
$$

A neural network applies these transformations successively across its
layers, with the output of one layer becoming the input to the next.

## From-Scratch Implementation

The notebook builds a neural network from its basic components and
implements the forward propagation process.

The implementation demonstrates how inputs are transformed through multiple
layers using weights, biases, and activation functions.

## What I Learned

- How individual neurons form the basic building blocks of neural networks.
- How weights and biases transform the input at each layer.
- How activation functions introduce non-linearity.
- Why a single perceptron is limited to linear decision boundaries.
- How stacking layers allows a network to represent more complex
  relationships.
- How forward propagation transforms an input through a neural network.

## Notebook

[Open the Neural Network notebook](./neural_network.ipynb)