## Project Overview

This project focuses on **character-level text generation** using a **Recurrent Neural Network (RNN)**. The model is trained on a dataset of **William Shakespeare’s writings**, sourced from Andrej Karpathy’s article *“The Unreasonable Effectiveness of Recurrent Neural Networks”*. The objective is to learn character-level language patterns and generate new text that imitates Shakespearean writing style.

### Data Preprocessing
- Converted raw text into numerical representations using `tf.keras.layers.StringLookup`.
- Created supervised training examples by splitting the text into overlapping sequences of length `seq_length + 1`.
  - For example, given `seq_length = 4` and the text `"Hello"`:
    - **Input sequence:** `"Hell"`
    - **Target sequence:** `"ello"`
- Generated shuffled and batched training datasets for efficient model training.

### Model Architecture and Training
The character-based RNN model consists of:
- **Embedding layer** with a 256-dimensional embedding space
- **GRU layer** with 1024 units to capture sequential dependencies
- **Dense output layer** with a number of neurons equal to the total number of unique characters in the dataset

### Model Training
- The model was trained for **20 epochs** using character-level sequence prediction.
- Training focused on learning grammatical structure, punctuation, capitalization, and writing style.

### Results
- The trained model is able to generate **readable text** that demonstrates:
  - Appropriate capitalization
  - Paragraph structure
  - Vocabulary and stylistic patterns similar to Shakespeare
- Due to the relatively small number of training epochs, the model has not yet fully learned to produce **coherent, long-form sentences**, but it successfully captures the underlying character-level language structure.
