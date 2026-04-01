# CEG3004 Environmental Sound Classification

## Group
Pr_08

## Overview
This repository contains the final implementation for the CEG3004 DSP project on environmental sound classification.

The system classifies 50 environmental sound classes using an improved DSP-based feature extraction pipeline and an SVM classifier with dimensionality reduction and class balancing.


## Files
- `CEG3004_Project_Colab.ipynb` — final Colab notebook
- `Pr_08_model.joblib` — trained final model
- `Pr_08_predictions.csv` — prediction output
- `README.md` — project documentation


## Pipeline

### Preprocessing
The preprocessing stage performs:
- silence trimming
- fixed-length padding/truncation to 5 seconds
- RMS normalization
- pre-emphasis filtering

The code also includes optional augmentation support for robustness experiments, such as:
- random gain
- Gaussian noise
- mild pitch shifting
- slight speed perturbation


### Feature Extraction
The final feature set includes:
- MFCC (40 coefficients)
- delta MFCC
- delta-delta MFCC
- log-mel spectrogram
- spectral centroid
- spectral bandwidth
- spectral rolloff
- zero-crossing rate
- spectral contrast
- chroma features

Feature pooling is done using:
- mean
- standard deviation
- median
- 25th percentile
- 75th percentile

This expanded feature set was designed to capture both timbral and spectral variations in environmental sounds more effectively than a baseline MFCC-only approach.


## Model
The final model is:

- SMOTE for class balancing
- StandardScaler
- PCA for dimensionality reduction
- `SVC(kernel='rbf', class_weight='balanced')`

The model was optimized using `GridSearchCV` with 5-fold cross-validation.

Hyperparameters explored include:
- PCA components: 180, 200, 220
- SVM `C`: 200, 240, 280
- SVM `gamma`: 0.0007, 0.0005, 0.0003

The final configuration was selected based on validation Macro-F1.


## Experiments
The baseline notebook was improved through:
- preprocessing enhancements
- expanded feature extraction beyond baseline MFCC statistics
- addition of spectral and chroma-based descriptors
- robust statistical pooling
- class balancing with SMOTE
- dimensionality reduction with PCA
- comparison of different SVM hyperparameter settings using grid search

These experiments were carried out to improve generalization and robustness across the 50 sound classes.


## Best Validation Result
**Macro-F1: 0.6675720945720945**


## Reproducibility
To run the project:

1. Open the notebook in Google Colab
2. Run the cells from top to bottom
3. Install the required dependencies
4. Download and extract the dataset through the notebook
5. Set the correct `GROUP_ID`
6. Build the training feature matrix
7. Train the model using grid search
8. Generate the submission CSV

## Outputs
The notebook generates:
- prediction CSV file
- trained `.joblib` model file

- `Pr_08_predictions.csv`

Only the model file and prediction CSV are required for submission.
