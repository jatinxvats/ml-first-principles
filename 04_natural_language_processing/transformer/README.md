# Transformers

## Overview

Transformers are neural network architectures built around attention mechanisms rather than recurrence. They allow a model to process relationships between tokens directly and form the foundation of modern language models such as GPT.

In this topic, I built a Transformer-based language model from the ground up and used it to generate text from the Shakespeare corpus. The goal was to understand how the individual components fit together into a complete autoregressive language model.

---

## What I Studied

The implementation was built progressively, starting from the representation of tokens and ending with a GPT-style Transformer language model.

The main components were:

1. Shakespeare dataset and tokenization
2. Vocabulary construction
3. Batch generation
4. Token embeddings
5. Positional embeddings
6. Single-head self-attention
7. Multi-head self-attention
8. Feedforward network
9. Transformer block
10. GPT-style language model
11. Training and text generation

---

## Dataset

I used a Shakespeare text corpus for character-level language modeling.

The corpus was first processed to construct a vocabulary of the unique characters appearing in the dataset. Each character was mapped to an integer token, allowing the text to be represented as a sequence of numerical values.

The dataset was then divided into batches of input and target sequences for autoregressive training.

For each training example, the model receives a sequence of tokens and learns to predict the next token at every position.

---

## Token Embeddings

The integer token IDs were converted into dense vector representations using a learnable embedding layer.

Instead of operating directly on discrete character IDs, the Transformer therefore receives continuous vector representations for each token.

---

## Positional Embeddings

Self-attention by itself does not inherently encode the order of tokens.

To provide positional information, learnable positional embeddings were added to the token embeddings.

The resulting representation can be viewed conceptually as:

$$
\text{input representation}
=
\text{token embedding}
+
\text{positional embedding}
$$

This gives the model information about both **what** each token represents and **where** it occurs in the sequence.

---

## Single-Head Self-Attention

I implemented a single self-attention head to understand the fundamental mechanism behind Transformer architectures.

The input representations are projected into:

- Queries
- Keys
- Values

The queries and keys determine how strongly different positions should interact, while the values contain the information that is aggregated.

For the autoregressive language-modeling setting, the attention mechanism must be causal: a token cannot attend to future tokens.

This allows the model to use the preceding context while predicting the next token.

---

## Multi-Head Attention

I then extended single-head attention into multi-head attention.

Instead of performing one attention operation, multiple attention heads operate in parallel. Each head can learn different relationships between positions in the sequence.

Their outputs are combined to produce the final attention representation.

This forms the main mechanism through which the Transformer can model relationships between tokens.

---

## Feedforward Network

Following the attention mechanism, I implemented the position-wise feedforward network.

The feedforward network applies nonlinear transformations to the representation at each position independently.

The combination of:

**self-attention → feedforward network**

forms the core computational structure of a Transformer block.

---

## Transformer

The individual components were then combined into a Transformer architecture.

The model processes a sequence through:

1. Token and positional embeddings
2. Multi-head self-attention
3. Feedforward transformation
4. Output projection

The architecture is designed for autoregressive language modeling, so the model predicts the next token based only on the preceding context.

---

## GPT Model

I then assembled the Transformer into a GPT-style language model.

The model takes a sequence of tokens and produces logits over the vocabulary for every position.

During training, the predicted next-token distributions are compared against the actual next tokens using cross-entropy loss.

During generation, the model repeatedly predicts the next token, samples from the resulting distribution, and feeds the new token back into the model.

This allows the model to generate text autoregressively.

---

## Training

I trained the model on the Shakespeare corpus in two stages.

### Initial training

The first training run lasted **3,000 steps**, with the training loss observed at intervals of 500 steps.

The loss decreased throughout training, indicating that the model was learning to predict the next character more effectively.

### Extended training

I then continued with a longer training run of **7,000 steps**, observing the loss at intervals of 1,000 steps.

With additional training, the generated text increasingly began to resemble the statistical structure and style of the Shakespeare corpus.

---

## Observations

The most important observation from the experiment was the relationship between training loss and generated text.

Early generations were largely incoherent and showed little resemblance to Shakespearean writing.

As training progressed:

- the loss decreased,
- character sequences became more structured,
- common patterns in the corpus began appearing,
- generated text increasingly resembled dialogue and Shakespeare-like writing.

This made the progression from optimization to learned language structure directly observable.

The model was not explicitly given rules about Shakespearean grammar, dialogue, or character names. These patterns emerged from learning statistical relationships within the training corpus.

---

## What I Learned

This implementation helped connect the individual components of the Transformer architecture into a complete language model.

The main ideas I took away were:

- Token embeddings provide continuous representations of discrete tokens.
- Positional embeddings provide information about sequence order.
- Self-attention allows tokens to interact with other positions in the context.
- Multi-head attention allows several attention patterns to be learned in parallel.
- Feedforward networks transform the representations produced by attention.
- Causal masking makes the architecture suitable for autoregressive generation.
- These components can be assembled into a GPT-style language model.
- Training the model directly demonstrates how minimizing next-token prediction loss leads to increasingly structured generation.

Most importantly, I now have a working implementation connecting **attention → Transformer → GPT → language generation**, rather than treating GPT as a black box.

---