# Environmental Sound Classification (CEG3004 Project)

## Overview

This project implements a robust audio classification pipeline for Environmental Sound Classification using Digital Signal Processing (DSP) techniques and machine learning. The system is designed to perform accurately under clean, noisy, and band-limited conditions.

---

## Objectives

* Train on labeled environmental sound data
* Extract meaningful DSP-based audio features
* Classify audio into 50 sound categories
* Improve robustness under distortions (noise & bandwidth limitations)

---

## Dataset

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

## Methodology

### Preprocessing

* Audio loading and resampling
* Normalization
* Noise handling (if applied)

### Feature Extraction (DSP)

The following features were extracted:

* MFCCs (Mel-Frequency Cepstral Coefficients)
* Delta and Delta-Delta features
* Spectral Centroid
* Spectral Bandwidth
* Zero Crossing Rate
* Spectral Rolloff

### Model

* Feature Scaling using StandardScaler
* Dimensionality Reduction (PCA) *(if used)*
* Classifier: *(e.g., SVM / Random Forest / Logistic Regression)*

---

## Experiments & Improvements

| Experiment | Change                   | Result |
| ---------- | ------------------------ | ------ |
| Baseline   | MFCC only                | X%     |
| Exp 1      | Added delta features     | X%     |
| Exp 2      | Added noise augmentation | X%     |
| Final      | Full feature pipeline    | X%     |

---

## Results

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

