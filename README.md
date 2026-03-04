# PyTorch_Project_3-LSTM-Based-Next-Word_Predector

This project implements a **Next Word Prediction** model using **PyTorch** and an **LSTM (Long Short-Term Memory)** network.

The model is trained on a text corpus and predicts the next word given an input sequence.

---

## 📌 Project Overview

- Text preprocessing using **NLTK**
- Vocabulary creation with a custom `<unk>` token
- Custom `Dataset` and `DataLoader`
- LSTM-based neural network
- Training using CrossEntropyLoss and Adam optimizer
- Next word prediction function

---

## 🛠 Technologies Used

- Python
- PyTorch
- NLTK

---

## 📂 Data Processing

1. Text is tokenized using `nltk.word_tokenize`.
2. A vocabulary dictionary is created:
   - `<unk>` token for unknown words.
3. Sentences are converted into numerical indices.
4. Input sequences are padded.
5. Custom `Dataset` class is used to load training data.

---

## 🧠 Model Architecture

The model is defined as:

- **Embedding Layer**
  - Input: `vocab_size`
  - Output dimension: `100`

- **LSTM Layer**
  - Input size: `100`
  - Hidden size: `150`
  - `batch_first=True`

- **Fully Connected Layer**
  - Input: `150`
  - Output: `vocab_size`

---

## ⚙️ Training Configuration

- Epochs: `50`
- Learning Rate: `0.001`
- Loss Function: `CrossEntropyLoss`
- Optimizer: `Adam`
- Device: `CUDA` (if available) else `CPU`
- Batch Size: `32`

Training loop:
- Forward pass
- Loss computation
- Backpropagation
- Optimizer step

Loss is printed after each epoch.

---

## 🔮 Prediction

The `predection()` function:

1. Tokenizes input text
2. Converts words to indices
3. Pads the sequence
4. Feeds it into the trained model
5. Selects the word with maximum probability
6. Appends predicted word to the input text
