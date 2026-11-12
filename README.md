# Novel Bank Customer Churn Prediction

## Overview

| Summary Component | Description |
| :-------------: | ------ |
| **Dataset Size** | 10,000 customers |
| **Problem Type** | Binary Classification (Churn / No Churn) |
| **Tools Used** | Python, TensorFlow/Keras, scikit-learn, Streamlit |
| **Key Metric** | Validation Accuracy ~86.5% |
| **Outcome** | Trained ANN model and deployed a Streamlit app to predict customer churn probability. |

Jump to:
- [Executive Summary](#executive-summary)
- [Dataset & Preprocessing](#dataset--preprocessing)
- [Model Architecture & Training](#model-architecture--training)
- [Results](#results)
- [How to Run](#how-to-run)
- [Caveats & Next Steps](#caveats--next-steps)

# Project Background

Novel Bank wants to identify customers who are likely to churn so that retention efforts can be targeted more effectively. This project uses historical customer data to train an Artificial Neural Network (ANN) that predicts whether a customer will exit the bank.

The project covers:
- Data preprocessing and feature encoding
- Training and evaluating an ANN classifier
- Saving the model and preprocessing artifacts
- Deploying a Streamlit app for interactive churn prediction

**Business Question:** Can we predict which customers are likely to churn based on their profile and account activity?

# Executive Summary

A feedforward ANN was trained on Novel Bank’s 10,000-row customer dataset. The model uses customer attributes such as credit score, geography, gender, age, tenure, balance, number of products, card status, activity status, and estimated salary.

Key results from the notebook:
- **Validation accuracy:** ~86.5%
- **Validation loss:** ~0.3405
- **Training accuracy:** ~86.8%
- **Early stopping:** Used with patience of 10 epochs and best-weight restoration

The trained model and preprocessing objects are saved as:
- `model.keras`
- `scaler.pkl`
- `label_encoder_gender.pkl`
- `ohe_geo.pkl`

A Streamlit app allows users to enter customer details and receive a churn probability.

# Dataset & Preprocessing

- **Source:** `Churn_Modelling.csv`
- **Rows:** 10,000
- **Target:** `Exited` (1 = churned, 0 = retained)

Preprocessing steps:
1. Dropped unnecessary columns: `RowNumber`, `CustomerId`, `Surname`
2. Label-encoded `Gender`
3. One-hot encoded `Geography` into:
   - `Geography_France`
   - `Geography_Germany`
   - `Geography_Spain`
4. Split data into 80% training and 20% test/validation
5. Standard-scaled all features using `StandardScaler`

Saved preprocessing artifacts:
- `label_encoder_gender.pkl`
- `ohe_geo.pkl`
- `scaler.pkl`

# Model Architecture & Training

**Model type:** Sequential ANN

| Layer | Details |
| :--- | :--- |
| Input | 12 features |
| Hidden Layer 1 | Dense, 64 units, ReLU |
| Hidden Layer 2 | Dense, 32 units, ReLU |
| Output Layer | Dense, 1 unit, Sigmoid |
| Optimizer | Adam |
| Loss | Binary Crossentropy |
| Metric | Accuracy |
| Callbacks | EarlyStopping (patience=10, restore_best_weights=True), TensorBoard |

**Total parameters:** 2,945

Training used up to 100 epochs with early stopping. The model stopped after 12 epochs, restoring the best weights.

# Results

From `experiments.ipynb`:

- **Best validation accuracy:** ~86.5%
- **Best validation loss:** ~0.3405
- **Final training accuracy:** ~86.8%
- **Final training loss:** ~0.3216

Example prediction from `prediction.ipynb`:
- Input customer: CreditScore 600, France, Male, Age 30, Tenure 3, Balance 60,000, NumOfProducts 2, HasCrCard 1, IsActiveMember 1, EstimatedSalary 50,000
- Predicted churn probability: **0.0127**
- Interpretation: Customer is **not likely to churn**

# How to Run

## Streamlit App
Access the deployed app here:  
[https://novel-bank-ann-classification.streamlit.app/](https://novel-bank-ann-classification.streamlit.app/)