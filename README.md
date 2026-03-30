# 🎧 Environmental Sound Classification (CEG3004 Project)

## 📌 Overview

This project implements a robust audio classification pipeline for Environmental Sound Classification using Digital Signal Processing (DSP) techniques and machine learning. The system is designed to perform accurately under clean, noisy, and band-limited conditions.

---

## 🎯 Objectives

* Train on labeled environmental sound data
* Extract meaningful DSP-based audio features
* Classify audio into 50 sound categories
* Improve robustness under distortions (noise & bandwidth limitations)

---

## 📂 Dataset

The dataset is derived from the ESC-50 dataset and contains:

* 2000 audio clips
* 50 sound classes
* 40 samples per class
* Each clip is 5 seconds (mono audio)

### Evaluation Data Includes:

* Clean audio
* Noisy audio
* Band-limited audio

---

## ⚙️ Methodology

### 🔹 Preprocessing

* Audio loading and resampling
* Normalization
* Noise handling (if applied)

### 🔹 Feature Extraction (DSP)

The following features were extracted:

* MFCCs (Mel-Frequency Cepstral Coefficients)
* Delta and Delta-Delta features
* Spectral Centroid
* Spectral Bandwidth
* Zero Crossing Rate
* Spectral Rolloff

### 🔹 Model

* Feature Scaling using StandardScaler
* Dimensionality Reduction (PCA) *(if used)*
* Classifier: *(e.g., SVM / Random Forest / Logistic Regression)*

---

## 🧠 Experiments & Improvements

| Experiment | Change                   | Result |
| ---------- | ------------------------ | ------ |
| Baseline   | MFCC only                | X%     |
| Exp 1      | Added delta features     | X%     |
| Exp 2      | Added noise augmentation | X%     |
| Final      | Full feature pipeline    | X%     |

---

## 📊 Results

* Clean Accuracy: XX%
* Noisy Accuracy: XX%
* Band-limited Accuracy: XX%

### Key Observations

* Model performs best on clean data
* Noise robustness improved with feature augmentation
* Band-limited data remains challenging

---

## 📁 Repository Structure

```
├── notebooks/        # Colab notebook
├── src/              # Python scripts (if any)
├── results/          # Outputs and plots
├── experiments/      # Experiment logs
├── submission/       # GitHub link file
├── README.md
├── requirements.txt
```

---

## 🚀 Installation

```bash
pip install -r requirements.txt
```

---

## ▶️ How to Run

1. Open the notebook in Google Colab
2. Set your `TEAM_ID` correctly
3. Upload or mount dataset
4. Run all cells sequentially
5. Outputs generated:

   * `prediction.csv`
   * `model.joblib`

---

## 🔁 Reproducibility

* Python version: 3.x
* Libraries listed in `requirements.txt`
* Fixed random seed used *(if applicable)*

---

## ⚠️ Important Notes

* Do NOT modify clip IDs
* Ensure correct TEAM_ID before running
* Follow submission format strictly

---

## 👩‍💻 Author / Team

* Name: Hessa Ebrahim
* Course: BEng Computer Engineering
* Module: CEG3004

---

## 📌 Future Improvements

* Deep learning models (CNN on spectrograms)
* Data augmentation techniques
* Real-time audio classification

---

