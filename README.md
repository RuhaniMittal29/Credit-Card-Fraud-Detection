# Credit Card Fraud Detection

## Overview
This project focuses on detecting fraudulent credit card transactions using machine learning techniques. Fraud detection is crucial for financial institutions as it helps prevent monetary losses, protect customers, and maintain trust in digital payment systems. The goal of this project is to build predictive models that can accurately identify fraudulent transactions in a dataset of anonymized credit card transactions.

## Dataset
The dataset used in this project is the **Credit Card Fraud Detection Dataset (2023)**, which contains anonymized transactions labeled as either fraudulent (`1`) or non-fraudulent (`0`). Each transaction includes features such as `Amount`, `Time`, and anonymized principal components (`V1` to `V28`) derived from the original data to protect privacy.

- **Source:** [Kaggle - Credit Card Fraud Detection Dataset (2023)](https://www.kaggle.com/datasets/nelgiriyewithana/credit-card-fraud-detection-dataset-2023?resource=download)
- **Number of samples:** ~500,000 transactions
- **Target variable:** `Class` (0 = non-fraud, 1 = fraud)

## Project Workflow
1. **Data Preprocessing**
   - Split data into training, validation, and test sets (stratified to preserve class balance).
   - Handle skewed features with log transformations.
   - Create derived features such as binned transaction amounts (`AmountBin`) to improve model performance.

2. **Feature Engineering**
   - Log-transform `Amount` to reduce skew.
   - Bin `Amount` into quartiles to create a categorical feature.
   - Drop redundant features where necessary.

3. **Modeling**
   - Train multiple models:
     - Logistic Regression
     - Random Forest
     - Gradient Boosting
   - Combine models using a **Voting Ensemble** (hard voting) for robust predictions.
   - Evaluate models using **accuracy, precision, recall, F1-score**, and **confusion matrices**.

4. **Evaluation**
   - The Voting Ensemble achieved near-perfect performance on the validation set, with very few misclassifications.
   - Metrics confirm that the ensemble can reliably detect fraudulent transactions in the dataset.
