# 🎧 SentiWave: Low-Latency Streaming Emotion AI

SentiWave is a real-time multimodal framework designed for **Speech Emotion Recognition (SER)** in streaming environments. Unlike traditional offline models, SentiWave processes audio in **2-second chunks**, making it ideal for live applications such as call center analytics and human-computer interaction.

---

## 🚀 Key Features

### ⚡ Low-Latency Pipeline
Achieves a mean computational latency of **9.78 ms**, significantly faster than the human perception threshold (~200 ms).

### 🧩 Modular Architecture
Parallel processing of:
- **Whisper Tiny (ASR)**
- **Prosodic Feature Extraction** (Pitch, Energy, Zero-Crossing Rate)

### 🛡️ Error-Robust Classification
Fine-tuned **DistilBERT** model focuses on high-arousal keywords, maintaining confidence even when ASR transcription errors occur.

### 💻 Hardware Efficient
Runs efficiently on **standard CPUs** (tested on Google Colab) without requiring GPUs.

### 🔍 Explainable AI (XAI)
Integrated with:
- **SHAP**
- **Attention Maps**

Helps visualize the influence of vocal tempo and energy on predicted emotions.

---

## 🛠️ System Architecture

The system follows a **sequential multimodal pipeline**:

1. Speech input is captured in real time  
2. Audio is segmented into **2-second chunks**  
3. Speech is transcribed using **Whisper Tiny (ASR)**  
4. Prosodic features are extracted from audio  
5. Text + audio features are passed to the classifier  
6. Emotion prediction is generated  

This design allows **independent optimization** of ASR and NLP components.

---

## 📊 Performance Summary

- **Dataset**: CREMA-D (Crowd-Sourced Emotional Multimodal Actors Dataset)

- **Accuracy**: **32.00%**  
  _Reflects the lexical–prosodic disconnect in scripted datasets_

- **Recall (Anger)**: **0.75**  
  _Highly effective for escalation detection systems_

- **Robustness**:
  - Pearson Correlation: **r = 0.3928**
  - p-value: **0.0521**  
  _Indicates model confidence is statistically independent of ASR Word Error Rate (WER)_

---

## 💻 Tech Stack

- **Language**: Python 3.x  
- **Deep Learning**: PyTorch, Hugging Face Transformers (**DistilBERT**)  
- **Speech Processing**: Whisper Tiny, Librosa  

---

## 📜 Publication

Presented at **COMPUTATIA 2026**

### Authors
- Mopuri Rishitha  
- Madhumita K  
- M. Chandraleka  
- Rahul Raj M  

---

## ✨ Key Insight

Rather than maximizing accuracy on static datasets, SentiWave prioritizes:

- Low latency  
- Real-time usability  
- Robustness to ASR errors  

This makes it highly suitable for **practical, streaming AI applications**.
