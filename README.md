# Intrusion Detection System using Autoencoder + RNN

This repository contains code for a hybrid deep learning-based Intrusion Detection System (IDS) using an **Autoencoder + RNN pipeline** on the **CICIDS2017 dataset**. The system detects and classifies network attacks including DDoS, Port Scanning, Web Attacks, and more.

## 📂 Dataset

The project uses the **cleaned and preprocessed version** of the CICIDS2017 dataset:

- Downloaded as a ZIP file
- Extracted and used directly in Colab
- Main file: `cicids2017_cleaned.csv`

## 💡 Project Overview

This system consists of two stages:

1. **Autoencoder (AE)**  
   Used for unsupervised anomaly detection. Samples with reconstruction error above a threshold are considered suspicious.

2. **RNN (Recurrent Neural Network)**  
   Further classifies flagged anomalies into specific attack categories using a supervised learning approach.

## 🚀 How It Works

1. **Load and preprocess the data**
   - MinMax scaling
   - Label encoding

2. **Autoencoder Stage**
   - Detects anomalies using MSE threshold
   - Normal traffic bypasses further processing

3. **RNN Stage**
   - Receives only flagged samples
   - Predicts attack types: Bots, DDoS, DoS, Web Attacks, etc.

4. **Post-processing**
   - Final decision logic combines both AE and RNN outputs
   - Introduces "Other" class for uncertain predictions

## 🏷️ Attack Categories

| Label | Attack Type        |
|-------|---------------------|
| 0     | Bots                |
| 1     | Brute Force         |
| 2     | DDoS                |
| 3     | DoS                 |
| 4     | Normal Traffic      |
| 5     | Port Scanning       |
| 6     | Web Attacks         |
| 7     | Other (Ambiguous)   |

## 📊 Performance

Final evaluation on the full dataset:

- **Overall Accuracy:** 99.68%
- Classification report includes precision, recall, and F1-score
- Confusion matrix is visualized using Seaborn heatmap


## 📈 Inference on Novel Attacks

Tested separately on Novel attacks like:

- **Infiltration**: Detected with high accuracy
- **Heartbleed**: Fully detected and classified as "Other"

- scikit-learn
- TQDM
- Seaborn, Matplotlib

## 📁 Directory Structure

