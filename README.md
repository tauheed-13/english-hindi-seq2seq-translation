# english-hindi-seq2seq-translation
English → Hindi machine translation using a Seq2Seq (Encoder–Decoder) LSTM model with teacher forcing, implemented in TensorFlow/Keras.

## Problem Statement
Machine translation is a core NLP task. This project focuses on building 
a word-level English → Hindi translator using deep learning.

## Theory of Encoder & Decoder Models
The Encoder–Decoder architecture, also known as Sequence-to-Sequence (Seq2Seq), is a neural network framework used to transform one sequence into another. It is widely used in tasks such as 
machine translation, text summarization, and speech recognition, where the input and output sequences can have different lengths.

### Encoder
The encoder processes the input sequence and converts it into a fixed-length representation that captures the overall meaning of the input.
In this project:
- The encoder takes an English sentence as input.
- Each word is first converted into a dense vector using an Embedding layer.
- These vectors are then processed sequentially by an LSTM network.
The LSTM encoder produces two important outputs:
- Hidden state (h) – represents short-term information.
- Cell state (c) – represents long-term contextual information.
Together, these states act as a compressed representation of the entire input sentence and are passed to the decoder.

### Decoder
The decoder generates the output sequence one token at a time using the information provided by the encoder.
In this project:
- The decoder receives the encoder’s final hidden and cell states as its initial state.
- During training, the decoder uses teacher forcing, where the correct previous word is given as input at each time step.
- At each step, the decoder predicts the next Hindi word using an LSTM followed by a Softmax layer.
The decoding process continues until a special end token (_end) is generated or the maximum sequence length is reached.

### Training vs Inference
- Training Phase: The full target sentence is available. The decoder learns to predict the next word given the previous correct word (teacher forcing).
- Inference Phase: The decoder generates words one at a time, feeding its own previous prediction back as input until the end token is produced.

### Limitations
This implementation uses a basic Seq2Seq model without attention. As a result:
- Long sentences may lose important information.
- Translation quality may decrease for complex inputs.
These limitations can be addressed by adding an attention mechanism or switching to a Transformer-based architecture.

## Model Architecture
- Encoder: Embedding + LSTM
- Decoder: Embedding + LSTM + Dense
- Training technique: Teacher Forcing
- Loss: Sparse Categorical Crossentropy

## Dataset
- Parallel English–Hindi sentence pairs
- Start and End tokens added to target sentences
