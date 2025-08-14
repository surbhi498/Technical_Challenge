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

Model Evaluation
This project tackles spoken digit recognition (0–9) using lightweight audio features and a fast, interpretable model.
The dataset is Free Spoken Digit Dataset, split into training and test sets.

⚙️ Modeling Choices
Features: Log-Mel spectrogram statistics (mean, std, delta), ~120 dimensions per clip → efficient, low-latency input.

Model: Logistic Regression with L2 regularization — minimal computational footprint, ideal for rapid prototyping.

Why it works: Spoken digits have consistent phonetic patterns; compact spectral features + linear classifier capture these effectively.

## 📊 Model Performance

### **Cross-Validation Results**  
**CV Accuracy:** `0.9678`  
**Macro Avg F1:** `0.968`  

| Digit | Precision | Recall | F1-Score | Support |
|-------|-----------|--------|----------|---------|
| 0     | 0.978     | 0.970  | 0.974    | 270     |
| 1     | 0.977     | 0.959  | 0.968    | 270     |
| 2     | 0.967     | 0.963  | 0.965    | 270     |
| 3     | 0.928     | 0.956  | 0.942    | 270     |
| 4     | 0.993     | 0.989  | 0.991    | 270     |
| 5     | 0.989     | 0.989  | 0.989    | 270     |
| 6     | 0.947     | 0.919  | 0.932    | 270     |
| 7     | 0.981     | 0.974  | 0.978    | 270     |
| 8     | 0.949     | 0.970  | 0.960    | 270     |
| 9     | 0.971     | 0.989  | 0.980    | 270     |

---

### **Test Set Results**  
**Test Accuracy:** `0.9733`  
**Macro Avg F1:** `0.970`  

| Digit | Precision | Recall | F1-Score | Support |
|-------|-----------|--------|----------|---------|
| 0     | 0.97      | 1.00   | 0.98     | 30      |
| 1     | 1.00      | 0.97   | 0.98     | 30      |
| 2     | 1.00      | 1.00   | 1.00     | 30      |
| 3     | 0.96      | 0.90   | 0.93     | 30      |
| 4     | 0.97      | 1.00   | 0.98     | 30      |
| 5     | 1.00      | 1.00   | 1.00     | 30      |
| 6     | 0.90      | 0.90   | 0.90     | 30      |
| 7     | 1.00      | 1.00   | 1.00     | 30      |
| 8     | 0.97      | 0.97   | 0.97     | 30      |
| 9     | 0.97      | 1.00   | 0.98     | 30      |

---

**✅ Key Highlights**
- High accuracy on both training (CV) and test sets, indicating strong generalization.
- Most digits achieve near-perfect precision and recall.
- Slightly lower recall for digit `6` and digit `3`, indicating minor confusion in similar-sounding classes.
- Lightweight model — fast inference suitable for real-time spoken digit recognition.

🚀 Responsiveness
End-to-end inference time (feature extraction → prediction) is milliseconds once the model is loaded.

Suitable for real-time digit recognition.

🧠 LLM Collaboration
This solution was developed with step-by-step prompting, debugging, and architectural reasoning using an LLM.
The process included:

Feature & model selection advice

Code optimization & modular design

Debugging microphone integration

Improving evaluation pipeline & result clarity

💡 Creative Extensions
Optional microphone input for live testing

Potential to simulate noise and test robustness

Modular code for quick swap to other classifiers (SVM, CNN)
  

---

## 📹 Development Process Video

You can watch my development process here:  
[![Watch the video](https://img.youtube.com/vi/kDBGwjCuaR4/0.jpg)](https://youtu.be/kDBGwjCuaR4)


