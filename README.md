# EEG Eye-State Classification using Dimensionality Reduction and Machine Learning
This project investigates methods for classifying eye states (open vs. closed) from EEG recordings. The work focuses on preprocessing, dimensionality reduction, and evaluation of classical machine learning algorithms. Initial experiments highlight the difficulty of separating eye-state classes in low-dimensional linear spaces. Smoothing techniques improve accuracy, and future work will explore additional approaches to enhance signal quality and class separability. 

## 1. Problem Overview
EEG data is noisy, high-dimensional, and often non-linearly separable, making eye-state classification challenging. The goal of this project is to design a workflow that:
1. Cleans and prepares raw EEG data
2. Reduces dimensionality to extract patterns
3. Evaluates performance of machine learning classifiers
4. Investigates smoothing methods to improve performance

## 2. Data Preparation and Feature Extraction
The raw EEG data was cleaned and prepared for analysis. Next, dimensionality reduction was performed using PCA. After analysis, \(n=4\) principal components were selected. Althought this captured a meaningful portion of the variance (91%), the resulting representation remained poorly separable, limiting classifier performance. 

## 3. Classification Models
Three classifiers were evaluated on the PCA-transformed data:
- k-Nearest Neighbours (kNN)
- Support Vector Machine (SVM)
- Random Forest Classifier

All models achieved close to 50% accuracy, which is roughly equivalent to random guessing in a binary classification task. This confirmed that the PCA representation did not provide enough information to correctly extract any patterns for eye-state labels. 

## 4. Data Smoothing
To reduce noise, a moving average smoothing technique was applied:
- A sliding window was defined
- Each point was replaced with the mean value of the window
- Classification accuracy was recalculated on the smoothed data
This method significantly improved performance, reaching 66.7% acccuracy, showing that smoothing captures useful patterns not visible in raw PCA features.

Next, the focus will be on exploring additional smoothing or signal-enhancement techniques.

