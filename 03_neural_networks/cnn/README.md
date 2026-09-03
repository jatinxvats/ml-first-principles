# Convolutional Neural Network (MNIST)

## Question

Why are convolutional neural networks better suited to image data than a
standard fully connected neural network?

## Core Idea

A convolutional neural network (CNN) is designed to learn spatial patterns in
images.

Instead of connecting every input pixel directly to every neuron, convolutional
layers learn local patterns using filters. These learned features can then be
combined by deeper layers to perform classification.

For MNIST, the network learns features from \(28 \times 28\) handwritten digit
images and uses them to classify the images into ten digit classes.

## Architecture

The CNN consists of:

- Convolutional layer: 1 input channel → 32 filters
- ReLU activation
- Max pooling
- Convolutional layer: 32 input channels → 64 filters
- ReLU activation
- Max pooling
- Flattening
- Fully connected layer: \(64 \times 5 \times 5 \rightarrow 128\)
- ReLU activation
- Dropout with probability \(0.2\)
- Fully connected output layer: \(128 \rightarrow 10\)

The final layer produces ten logits, one for each MNIST digit class.

## Data Pipeline

Used the MNIST dataset with the following preprocessing:

- Converted images to tensors using `ToTensor()`
- Normalized the images using the MNIST mean and standard deviation
- Used batches of 64 images
- Shuffled the training data

## Training

The network was trained using:

- Cross-Entropy Loss
- Adam optimizer
- Learning rate: \(0.001\)
- 10 training epochs

The number of trainable parameters was also calculated to understand the
size of the network.

## Evaluation

Tracked both training and test performance throughout training.

The following were recorded for each epoch:

- Training loss
- Test loss
- Training accuracy
- Test accuracy

These values were plotted to visualize how the network learned over the ten
epochs and to compare its behavior on training and unseen test data.

## What I Learned

- CNNs use convolutional filters to learn spatial features from images.
- Multiple convolutional layers allow the network to progressively build more
  useful representations.
- ReLU introduces non-linearity between convolutional operations.
- Max pooling reduces the spatial dimensions of feature maps.
- Flattening converts the learned feature maps into a representation that can
  be passed to fully connected layers.
- Dropout can be used to reduce over-reliance on individual neurons during
  training.
- The final fully connected layer produces logits for the ten digit classes.
- Tracking both training and test performance gives insight into how the model
  learns and generalizes.
- Counting parameters provides a concrete measure of the model's complexity.

## Notebook

[Open the CNN notebook](./cnn.ipynb)