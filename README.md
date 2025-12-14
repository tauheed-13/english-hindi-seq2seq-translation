# english-hindi-seq2seq-translation
English → Hindi machine translation using a Seq2Seq (Encoder–Decoder) LSTM model with teacher forcing, implemented in TensorFlow/Keras.

## Problem Statement
Machine translation is a core NLP task. This project focuses on building 
a word-level English → Hindi translator using deep learning.

## Model Architecture
- Encoder: Embedding + LSTM
- Decoder: Embedding + LSTM + Dense
- Training technique: Teacher Forcing
- Loss: Sparse Categorical Crossentropy

## Dataset
- Parallel English–Hindi sentence pairs
- Start and End tokens added to target sentences

