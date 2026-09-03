# MNIST

## Question

Can the neural-network concepts studied so far be combined to recognize
handwritten digits from images?

## Core Idea

MNIST is a dataset of handwritten digit images representing the digits 0
through 9.

Each image is used as input to a neural network, which learns to map the
pixel values to one of ten digit classes.

This experiment brings together the neural-network components studied earlier:
forward propagation, activation functions, loss functions, backpropagation,
optimization, and parameter updates.

## Experiment

Built and trained a neural network on the MNIST dataset.

The network was trained for **10 epochs** and evaluated on the test data to
measure its ability to generalize to handwritten digits it had not seen during
training.

### Misclassified Digits

After training, examined the digits that the network classified incorrectly.

Rather than looking only at the overall performance, the misclassified
examples were inspected individually to understand what kinds of handwritten
digits were difficult for the network to distinguish.

This provided a more concrete view of the model's errors and limitations.

## What I Learned

- How a neural network can learn to classify image data.
- How pixel values can be used as numerical input to a neural network.
- How the concepts studied individually combine into a complete training
  pipeline.
- Why evaluating only aggregate performance does not fully explain model
  behavior.
- Examining misclassified examples can reveal patterns in a model's errors
  that a single evaluation metric cannot show.
- Some handwritten digits are inherently more difficult to distinguish because
  of similarities in their shapes and writing styles.

## Notebook

[Open the MNIST notebook](./mnist.ipynb)