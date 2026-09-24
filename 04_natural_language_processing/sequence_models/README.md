# Sequence Models

This topic explores neural networks designed to model sequential data, focusing on Recurrent Neural Networks (RNNs) and Long Short-Term Memory (LSTM) networks.

The notebooks progress from implementing a vanilla RNN from scratch to using an LSTM and comparing their ability to learn sequential patterns and context.

## Concepts

- Sequential data
- Recurrent Neural Networks (RNNs)
- Hidden states
- Backpropagation Through Time (BPTT)
- Exploding gradients
- Gradient clipping
- Long Short-Term Memory (LSTM)
- Sigmoid and tanh activations
- Sequence generation

## 1. Recurrent Neural Network

### Implementation

A vanilla RNN was implemented from scratch, including:

- Forward propagation through a sequence
- Hidden state updates
- Backpropagation Through Time (BPTT)
- Gradient computation
- Gradient clipping to prevent exploding gradients

The model was then trained on a small text corpus, with training loss tracked throughout the process.

## 2. Long Short-Term Memory

An LSTM was implemented using PyTorch, using the sigmoid and tanh activation functions that form the basis of its gating mechanism.

The LSTM was first trained on the same small corpus used for the RNN. *Although the training loss decreased, the model produced similar results to the RNN on this simple dataset.*

The experiment was then extended to a larger Shakespeare text corpus.

Both the RNN and LSTM were trained on the larger corpus and their generated text was compared.

### Observations

The RNN continued to exhibit difficulty maintaining meaningful context as the sequence became more complex.

The LSTM, in contrast, was able to retain relevant contextual information over longer sequences and produced substantially more coherent generated text.

## Key Takeaways

- RNNs maintain sequential information through recurrent hidden states.
- Backpropagation Through Time allows the RNN to learn from sequential dependencies but can lead to unstable gradients.
- Gradient clipping helps control exploding gradients during RNN training.
- LSTMs introduce gating mechanisms to better control what information is retained and forgotten.
- On a small corpus, the difference between RNN and LSTM may not be immediately apparent.
- On a larger and more complex corpus, the LSTM demonstrated a stronger ability to maintain contextual information and generate coherent text.

## Notebooks

- `rnn.ipynb` — RNN implemented from scratch with BPTT and gradient clipping.
- `lstm.ipynb` — LSTM implementation and comparison with RNN on small and large text corpora.