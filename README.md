# Technical_Challenge
# 🎙️ Spoken Digit Recognition (0–9) – Lightweight Prototype

This project implements a **fast, lightweight** machine learning pipeline for recognizing **spoken digits (0–9)** from audio.  
It uses **Log-Mel Spectrogram features** + **Logistic Regression** and can work on pre-recorded `.wav` files or live microphone input.

---

## 📌 Features

- **Feature extraction**: Compact log-mel spectrogram + delta features (≈120 dimensions).
- **Classifier**: Logistic Regression for speed & simplicity.
- **Cross-validation**: Evaluates performance on training set.
- **Generalization test**: Uses a separate test split.
- **Optional microphone mode**: Live speech recognition.
- **Lightweight**: Trains in seconds, minimal dependencies.

---

## 📂 Dataset

This project uses the [Free Spoken Digit Dataset (FSDD)](https://huggingface.co/datasets/mteb/free-spoken-digit-dataset),  
accessed from the HuggingFace dataset repository:

- Train split:  
  `hf://datasets/mteb/free-spoken-digit-dataset/data/train-00000-of-00001.parquet`
- Test split:  
  `hf://datasets/mteb/free-spoken-digit-dataset/data/test-00000-of-00001.parquet`

---

