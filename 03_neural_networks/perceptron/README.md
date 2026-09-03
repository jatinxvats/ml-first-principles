# Perceptron

## Question

How can a simple computational model learn to separate two classes using a
linear decision boundary?

## Core Idea

The perceptron is one of the simplest neural network models.

It computes a weighted sum of its inputs and passes the result through a
step function to produce a binary prediction.

The model learns by adjusting its weights whenever it makes an incorrect
prediction.

The resulting decision boundary is linear, meaning that a perceptron can
only correctly classify data that is linearly separable.

## Mathematics

The perceptron computes:

$$
z = w^T x + b
$$

The prediction is obtained using a step function:

$$
\hat{y} =
\begin{cases}
1 & \text{if } z \geq 0 \\
0 & \text{otherwise}
\end{cases}
$$

When the prediction is incorrect, the weights are updated according to the
perceptron learning rule:

$$
w \leftarrow w + \eta(y-\hat{y})x
$$

and the bias is updated as:

$$
b \leftarrow b + \eta(y-\hat{y})
$$

where \(\eta\) is the learning rate.

## From-Scratch Implementation

The notebook implements a perceptron from scratch, including the prediction
function, step activation, error calculation, and weight updates.

The model is first trained on a simple linearly separable dataset.

## Experiment

After successfully training the perceptron on linearly separable data, the
experiment deliberately introduces the **XOR problem**.

XOR is not linearly separable, so no single straight-line decision boundary
can correctly separate all of its points.

The perceptron therefore fails to converge to a solution that perfectly
classifies the XOR data.

This demonstrates a fundamental limitation of the single-layer perceptron:
it can only learn linear decision boundaries.

## What I Learned

- How a perceptron converts weighted inputs into a binary prediction.
- How the perceptron learning rule updates weights after incorrect
  predictions.
- Why the perceptron can solve linearly separable classification problems.
- Why XOR cannot be solved by a single perceptron.
- How deliberately breaking a model can reveal the assumptions and
  limitations built into it.
- Why moving beyond a single perceptron requires introducing additional
  layers and non-linear transformations.

## Notebook

[Open the Perceptron notebook](./perceptron.ipynb)