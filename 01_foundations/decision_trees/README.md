# Decision Trees

## Question

How can we make predictions by recursively splitting data according to
feature values?

## Core Idea

A decision tree makes predictions by dividing the feature space into smaller
regions through a sequence of decision rules.

At each node, the algorithm evaluates possible splits and selects the one that
produces the greatest improvement in the purity of the resulting groups.

The process continues recursively, producing a tree of decision rules that
eventually leads to leaf nodes containing the final predictions.

## Mathematics

For classification, the impurity of a node can be measured using entropy:

$$
H(S) = -\sum_{k=1}^{K} p_k \log_2(p_k)
$$

where \(p_k\) is the proportion of samples belonging to class \(k\).

A split is evaluated using information gain:

$$
IG(S,A) = H(S) - \sum_{v \in Values(A)}
\frac{|S_v|}{|S|}H(S_v)
$$

The algorithm selects the split with the highest information gain and
recursively applies the same process to the resulting subsets.

## From-Scratch Implementation

The notebook explores the process of constructing a decision tree from scratch, 
including calculating entropy, evaluating candidate splits, and
using information gain to determine the best split.

## What I Learned

- How decision trees represent a prediction problem as a sequence of
  decision rules.
- How entropy measures the uncertainty within a set of samples.
- How information gain measures the usefulness of a potential split.
- How the best split is selected at each node.
- How recursive splitting produces the final tree structure.
- Why unrestricted tree growth can lead to overfitting.
- How controlling tree complexity affects generalization.

## Notebook

[Open the Decision Trees notebook](./decision_trees.ipynb)