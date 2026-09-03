# PyTorch

## Question

How can the neural networks and training concepts studied from first principles
be implemented using a modern deep learning framework?

## Core Idea

PyTorch provides the building blocks needed to construct, train, and evaluate
neural networks.

It handles operations such as tensor computation, automatic differentiation,
and parameter optimization while allowing the structure of the network and
training process to be explicitly defined.

## XORNet

Built an XOR neural network in PyTorch to connect the earlier from-scratch
implementation of XOR with a deep learning framework.

The network was trained to learn the non-linear decision boundary required by
the XOR problem.

This provided a practical transition from manually implementing neural-network
components to using PyTorch's abstractions.

## Classification Network

After building XORNet, built a classification network in PyTorch for a
classification task.

The network was trained using a standard neural-network training pipeline,
connecting:

- Forward propagation
- Loss calculation
- Backpropagation
- Optimization
- Parameter updates

## What I Learned

- How neural networks are represented using PyTorch.
- How tensors form the basic computational objects in PyTorch.
- How network architectures can be defined using PyTorch modules.
- How the forward pass produces predictions.
- How loss and backpropagation fit into the PyTorch training loop.
- How an optimizer updates the network's parameters.
- How the concepts previously implemented from scratch translate into a
  practical deep-learning framework.
- The difference between understanding the underlying mathematics and using a
  framework that automates much of the computation.

## Notebook

[Open the PyTorch notebook](./pytorch.ipynb)