# Attention

This topic explores **self-attention**, the mechanism that allows a model to determine which parts of a sequence are relevant to each other.

The implementation builds self-attention from scratch using query, key, and value representations, followed by scaled dot-product attention and softmax normalization.

## Concepts

- Self-attention
- Query, Key, and Value representations
- Query-Key similarity
- Attention scores
- Softmax
- Attention weights
- Attention weight matrices
- Semantic structure in embeddings

## Implementation

Self-attention was implemented from scratch using the following process:

1. Generate input representations.
2. Construct query, key, and value representations.
3. Compute query-key similarity scores.
4. Scale the attention scores.
5. Apply softmax to obtain attention weights.
6. Use the attention weights to combine the value representations.
7. Inspect the resulting attention weight matrix.

The implementation was first trained on randomly generated data to verify that the attention mechanism could learn meaningful weight distributions.

## Semantic Structure

To make the behavior of attention more interpretable, a simulated set of word embeddings was constructed with an underlying semantic structure.

The experiment then simulated trained query and key projection matrices and used them to produce an attention weight matrix.

This demonstrated how the learned query and key representations can determine which tokens attend more strongly to one another based on their relationships in the representation space.

## Key Takeaways

- Self-attention allows each token to assign different levels of importance to other tokens.
- Queries and keys determine the similarity between tokens.
- Softmax converts the attention scores into normalized attention weights.
- Values are combined according to these attention weights to produce the output representation.
- The attention weight matrix provides a direct view of which tokens attend to which other tokens.
- The behavior of attention depends on the representations learned by the query and key projections.

## Notebook

The accompanying notebook contains the complete from-scratch implementation and experiments:

`self_attention.ipynb`