# Word Embeddings

This topic explores how words can be represented as numerical vectors and how relationships between words can emerge from their surrounding context.

The implementation builds a simplified Word2Vec model from scratch, following the complete training process from corpus preparation to learned word representations.

## Concepts

- Vocabulary construction
- Word-to-index mappings
- Context windows
- Skip-gram
- Word2Vec
- Word embeddings
- Softmax
- Forward propagation
- Backpropagation
- Vector arithmetic

## Implementation

A small text corpus was used to build the training data.

The process was implemented step by step:

1. Build the vocabulary from the corpus.
2. Map words to integer indices.
3. Generate Skip-gram `(center word, context word)` training pairs.
4. Initialize the Word2Vec parameters.
5. Perform the forward pass.
6. Apply softmax to obtain predicted context-word probabilities.
7. Compute the training loss.
8. Perform the backward pass to calculate gradients.
9. Update the model parameters.
10. Extract the learned word vectors.

The Word2Vec model was implemented using **softmax**, without relying on a pre-built embedding implementation.

## Vector Arithmetic

After training, the learned embeddings were used to explore relationships between words through vector arithmetic.

The experiments demonstrate how operations on word vectors can capture relationships present in the learned representation space.

## Key Takeaways

- Words can be represented as dense numerical vectors.
- Skip-gram learns word representations by predicting surrounding context from a target word.
- The embedding matrix learned during training provides the numerical representation of each word.
- The forward and backward passes allow the embeddings to be learned directly from contextual relationships.
- Relationships between words can be explored through operations on their learned vectors.

## Notebook

The accompanying notebook contains the complete implementation and experiments:

`word2vec.ipynb`