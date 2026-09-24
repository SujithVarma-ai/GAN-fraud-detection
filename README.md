# GAN-Based Fraud Detection

GAN-based synthetic fraud data generation for addressing class imbalance and improving credit card fraud detection.

## 📌 Project Overview

Credit card fraud detection is a highly imbalanced classification problem where fraudulent transactions represent a very small proportion of total transactions.

This project investigates whether Generative Adversarial Networks (GANs) can learn the distribution of fraudulent transactions and generate synthetic fraud data that can be used to augment the training data of a fraud detection model.

## 🎯 Objectives

- Analyze and clean the credit card transaction dataset
- Handle severe fraud-class imbalance
- Train a GAN using real fraudulent transactions
- Generate synthetic fraudulent transactions
- Evaluate the quality and diversity of generated data
- Measure the impact of synthetic fraud data on fraud detection
- Compare baseline and GAN-augmented fraud detection models
- Experiment with WGAN-GP for improved generative modeling

## 📊 Dataset

**Dataset:** Credit Card Fraud Detection

The dataset contains:

- 284,807 original transactions
- 284,315 legitimate transactions
- 492 fraudulent transactions
- 30 input features
- 1 target variable (`Class`)

The dataset contains anonymized PCA-transformed features (`V1`–`V28`), along with `Time` and `Amount`.

## 🔬 Current Progress

### Stage 1 — Dataset Collection & Setup
- Dataset downloaded and loaded
- Dataset structure inspected
- Missing values checked
- Class distribution analyzed

### Stage 2 — Exploratory Data Analysis
- Duplicate transactions analyzed
- Duplicate frequency investigated
- Legitimate and fraudulent duplicate transactions analyzed
- Transaction amount distribution explored

### Stage 3 — Data Cleaning
- Missing values verified
- Invalid values checked
- Exact duplicate rows removed
- 1,081 extra duplicate copies removed

Cleaned dataset:

- 283,726 total transactions
- 283,253 legitimate
- 473 fraudulent

### Stage 4 — Data Preprocessing
- Features and target separated
- 80/20 stratified train-test split performed
- Training features scaled using `StandardScaler`
- 378 fraudulent training transactions extracted
- Fraud data prepared using PyTorch `DataLoader`

### 🔒 Data Leakage Prevention

The test set is kept completely separate from GAN training and preprocessing.

Training:
- 226,980 transactions
- 226,602 legitimate
- 378 fraudulent

Testing:
- 56,746 transactions
- 56,651 legitimate
- 95 fraudulent

The test set will only be used for final evaluation.

## 🚧 Upcoming Work

- Baseline fraud detection model
- Vanilla GAN implementation
- Synthetic fraud generation
- Synthetic data quality evaluation
- GAN-based data augmentation
- WGAN-GP implementation
- Baseline vs GAN comparison
- Final evaluation on unseen real transactions

## 🛠️ Technologies

- Python
- Pandas
- NumPy
- Scikit-learn
- PyTorch
- Matplotlib
- Google Colab
- Git & GitHub
