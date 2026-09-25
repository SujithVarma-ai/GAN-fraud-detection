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
- Experiment with WGAN-GP and compare its performance with the vanilla GAN

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

### Stage 5 — Baseline Fraud Detection
- Baseline Logistic Regression classifier implemented
- Class imbalance handled using class_weight="balanced"
- Baseline predictions generated on the unseen test set
- Confusion matrix generated
- Accuracy, Precision, Recall, F1-Score, and ROC-AUC calculated
- Classification report generated
- Confusion matrix visualized

### Stage 6 — Vanilla GAN
- Generator network implemented using PyTorch
- Discriminator network implemented using PyTorch
- Binary Cross-Entropy loss and Adam optimizers configured
- Vanilla GAN trained using 378 real fraudulent training transactions
- Generator and Discriminator training losses recorded
- GAN training loss curves visualized
- 1,000 synthetic fraudulent transactions generated

### Stage 7 — Synthetic Data Evaluation
- Synthetic fraud data converted to DataFrame
- Generated data converted back to original feature scale
- Real vs synthetic fraud statistics compared
- Real and synthetic feature distributions visualized
- Exact-match check performed to detect memorization
- Synthetic transaction validity checked
- Negative Amount values in generated transactions investigated
  
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

## 🔄 Project Workflow

```text
Credit Card Transactions
          ↓
   Exploratory Analysis
          ↓
      Data Cleaning
          ↓
   Train/Test Split
          ↓
     Feature Scaling
          ↓
   378 Real Fraud Samples
          ↓
      Vanilla GAN
          ↓
 Synthetic Fraud Generation
          ↓
   Synthetic Data Evaluation
          ↓
    Fraud Classifier
          ↓
   Final Evaluation on
   Unseen Real Test Data
          ↓
       WGAN-GP
          ↓
   Model Comparison
```

## 💡 Why This Project?

Fraudulent transactions are extremely rare compared with legitimate transactions, making fraud detection a severe class-imbalance problem.

In the original dataset, only 492 out of 284,807 transactions are fraudulent.

This project explores whether synthetic fraud generation using GANs can provide additional minority-class data and improve downstream fraud detection without compromising evaluation integrity.


### Add the dataset source

```markdown
## 📚 Dataset Source
```

The project uses the **Credit Card Fraud Detection** dataset originally provided by the Machine Learning Group of ULB and distributed through Kaggle.

The dataset is used for research and educational purposes. Refer to the original dataset source for its licensing and usage terms.

## 📌 Project Status

🚧 **In Development**

Completed:
- [x] Dataset collection
- [x] Exploratory data analysis
- [x] Data cleaning
- [x] Train/test split
- [x] Feature scaling
- [x] Fraud data preparation

In progress:
- [ ] Baseline fraud detection
- [ ] Vanilla GAN
- [ ] Synthetic data evaluation
- [ ] WGAN-GP
- [ ] Final comparison

## ⚠️ Dataset Limitations

The dataset contains anonymized PCA-transformed features and represents transactions collected over a limited historical period.

Therefore, results from this project should be interpreted as experimental findings on the benchmark dataset and should not be assumed to directly represent performance on modern real-world banking transactions.

## 🛠️ Technologies

- Python
- Pandas
- NumPy
- Scikit-learn
- PyTorch
- Matplotlib
- Google Colab
- Git & GitHub
