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
