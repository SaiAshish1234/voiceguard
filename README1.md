# 🎙️ VoiceGuard — Real-Time Deepfake Audio Detector

> Detects AI-generated and cloned voices in real time using CNN+LSTM on mel spectrograms — with a live phone call scanning pipeline.

![Python](https://img.shields.io/badge/Python-3.10+-blue) ![PyTorch](https://img.shields.io/badge/PyTorch-2.2-orange) ![Dataset](https://img.shields.io/badge/Dataset-ASVspoof%202019-red) ![Streamlit](https://img.shields.io/badge/Streamlit-App-green)

---

## 🎯 Problem Statement

AI voice scams cost Indians ₹1,200+ crore in 2024. Existing solutions only work on pre-recorded files. VoiceGuard scans calls **in real time** — the same way antivirus scans files as they're opened, not after.

---

## 🏗️ Project Structure

```
voiceguard/
├── notebooks/
│   ├── week1_colab.ipynb   ← Data + Feature Extraction
│   ├── week2_colab.ipynb   ← CNN+LSTM Model Training
│   ├── week3_colab.ipynb   ← Real-Time Pipeline
│   └── week4_colab.ipynb   ← Dashboard + Deployment
├── src/
│   ├── features.py         # Audio feature extraction
│   ├── model.py            # CNN+LSTM architecture
│   └── realtime.py         # WebSocket streaming pipeline
├── app/
│   └── streamlit_app.py    # Live dashboard
└── requirements.txt
```

---

## 🗓️ Built Week by Week

| Week | Focus | Status |
|---|---|---|
| 1 | Data + Feature Extraction | ✅ Done |
| 2 | CNN+LSTM Model Training | 🔄 In progress |
| 3 | Real-Time Streaming Pipeline | ⏳ Coming |
| 4 | Dashboard + Deployment | ⏳ Coming |

---

## 📌 Dataset

[ASVspoof 2019 LA](https://datashare.ed.ac.uk/handle/10283/3336) — 25K+ audio files, 11 AI attack types
