# 🎙️ VoiceGuard — Deepfake Audio Detection

**Detecting AI-generated and cloned voices through audio signal processing and machine learning.**

VoiceGuard is an AI/ML and cybersecurity project focused on identifying synthetic speech and voice-cloning attacks. The goal is to build a system that can analyze audio, estimate whether it is genuine or spoofed, and eventually support low-latency detection through a live dashboard.

> **Project status:** Week 1 — Dataset exploration and baseline feature extraction completed. Model training and real-time inference are planned next.

## 🎯 Objectives

- Extract informative acoustic features from genuine and synthetic speech.
- Train machine learning models to distinguish bonafide speech from spoofed audio.
- Evaluate performance using Equal Error Rate (EER), ROC-AUC, precision, and recall.
- Develop a real-time audio analysis pipeline and interactive dashboard.
- Explore the challenges of detecting cloned voices under realistic recording conditions.

## 🧠 How It Works

The planned detection pipeline is:

1. **Audio input:** Load a recording or capture audio from a supported input source.
2. **Preprocessing:** Standardize the sample rate and prepare audio segments.
3. **Feature extraction:** Compute MFCCs, mel spectrograms, and other spectral statistics.
4. **Classification:** Predict whether an audio segment is bonafide or spoofed.
5. **Evaluation and visualization:** Display model confidence, performance metrics, and relevant audio visualizations.

The initial model will use handcrafted acoustic features. A CNN-based model using log-mel spectrograms will be explored separately.

## 📊 Dataset

**ASVspoof 2019 — Logical Access (LA)**

The project currently uses the ASVspoof 2019 LA dataset, which contains genuine speech and spoofed speech generated using various synthesis and voice-conversion systems.

The Week 1 notebook downloads and inspects the dataset, reads its protocol files, and extracts a configurable subset for experimentation.

Dataset access and usage are subject to the dataset provider's terms.

## ✅ Progress

### Week 1 — Data and Feature Engineering

- [x] Download and inspect the ASVspoof 2019 LA dataset.
- [x] Parse protocol files and map bonafide/spoof labels.
- [x] Analyze class distributions.
- [x] Visualize waveforms, mel spectrograms, and MFCCs.
- [x] Implement a 455-dimensional statistical feature extraction pipeline.
- [x] Extract 5,000 balanced training samples.
- [x] Extract 2,000 development samples while preserving the sampled class distribution.
- [x] Save feature arrays, labels, file IDs, and metadata to Google Drive.
- [ ] Train and evaluate the first baseline classifier.

### Week 2 — Model Development

- [ ] Train a Logistic Regression baseline.
- [ ] Evaluate ROC-AUC, EER, precision, recall, and confusion matrix.
- [ ] Establish a reproducible evaluation pipeline.
- [ ] Experiment with a CNN on log-mel spectrograms.

### Week 3 — Streaming Prototype

- [ ] Implement chunk-based audio inference.
- [ ] Develop an API for streaming predictions.
- [ ] Measure inference latency and prediction stability.

### Week 4 — Dashboard and Deployment

- [ ] Build an interactive dashboard.
- [ ] Add recorded-audio analysis.
- [ ] Integrate the trained model with the application.
- [ ] Deploy a working prototype and record a demonstration.

*The roadmap is a development plan; unchecked items are not yet implemented.*

## 🛠️ Technology Stack

| Component | Tools |
|---|---|
| Language | Python |
| Audio processing | Librosa, SoundFile |
| Data analysis | NumPy, Pandas, Matplotlib |
| Machine learning | Scikit-learn |
| Deep learning (planned) | PyTorch |
| Notebook environment | Google Colab |
| API (planned) | FastAPI, WebSockets |
| Dashboard (planned) | Streamlit |

## 📁 Repository Structure

```text
voiceguard/
├── notebooks/
│   ├── README.md
│   └── voiceguard_week1.ipynb
├── .gitignore
├── README.md
├── requirements.txt
└── README1.md
```

`README1.md` is the original repository documentation and can be removed after this README is committed and verified.

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/SaiAshish1234/voiceguard.git
cd voiceguard
```

### 2. Set up Python

Create and activate a virtual environment, then install the project dependencies:

```bash
python -m venv .venv
```

Windows:

```bash
.venv\Scripts\activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

### 3. Run the Week 1 notebook

Open [`notebooks/voiceguard_week1.ipynb`](notebooks/voiceguard_week1.ipynb) in Google Colab.

The notebook currently uses Google Colab paths and Google Drive for dataset processing and artifact storage. Follow the notebook's setup instructions before rerunning it.

## 📈 Evaluation Strategy

VoiceGuard will use metrics appropriate for an imbalanced binary classification problem:

- **Equal Error Rate (EER):** The operating point where false acceptance and false rejection rates are equal.
- **ROC-AUC:** Measures how well the model ranks bonafide and spoofed samples.
- **Precision and recall:** Help characterize spoof detections and missed attacks.
- **Confusion matrix:** Shows the types and counts of classification errors.

No detection-performance claims are made until the baseline has been trained and evaluated on held-out data.

## ⚠️ Limitations

- The current implementation is a feature extraction and data analysis pipeline, not a completed deepfake detector.
- The current experiment uses a subset of ASVspoof 2019 LA; generalization to unseen synthesis methods and real-world phone calls remains to be tested.
- Live phone-call integration is a future goal and is not currently implemented.
- Predictions from a future model should be treated as risk estimates, not definitive proof that a voice is genuine or synthetic.

## 🔐 Responsible Use

VoiceGuard is intended for research, education, and defensive security. It should complement other verification methods rather than replace identity checks or human judgment. Audio data should be handled with appropriate consent and privacy protections.

## 👨‍💻 Author

**Sai Ashish**

- GitHub: [@SaiAshish1234](https://github.com/SaiAshish1234)

---

*VoiceGuard is an ongoing project exploring audio forensics, machine learning, and defensive cybersecurity.*
