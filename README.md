# Predicting Scientific Article Citation Count Using Machine Learning

## Overview

This project predicts the future citation count of scientific articles using Machine Learning techniques. The goal is to estimate the scientific impact of a research paper based only on information available before citations accumulate.

Two regression models were implemented and compared:

- k-Nearest Neighbors (kNN)
- Neural Network (PyTorch)

---

## Dataset

**Source:** Kaggle – Research Citation Network

The original dataset contains approximately **250,000 scientific papers**.

After data cleaning and preprocessing, **100,000 papers** were selected for training and evaluation.

### Available Features

- Title
- Abstract
- Authors
- Publication Year
- Venue
- Keywords
- References
- Citation Count

---

## Data Preprocessing

The following preprocessing steps were applied:

- Removed missing values
- Removed duplicate records
- Selected English-language papers
- Filtered Journal and Conference publications

### Feature Engineering

Additional features were created:

- Paper Age
- Authors Count
- Reference Count
- Keywords Count
- Title Length
- Abstract Length

---

## Feature Processing Pipeline

Different preprocessing techniques were applied depending on the feature type.

### Numerical Features

- StandardScaler

### Categorical Features

- OneHotEncoder

### Text Features

- TF-IDF Vectorization

### Dimensionality Reduction

- Truncated SVD (25 Components)

---

## Machine Learning Models

### k-Nearest Neighbors (kNN)

- Regression model
- Best value of **k** selected using validation data

### Neural Network

Architecture:

- Input Layer
- Hidden Layer (16 neurons)
- ReLU Activation
- Output Layer
- Softplus Activation

Optimizer:

- Adam

Loss Function:

- Mean Squared Error (MSE)

Early stopping was used to prevent overfitting.

---

## Model Evaluation

The models were evaluated using:

- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- R² Score

### Results

| Model | MAE | RMSE | R² |
|------|------:|------:|------:|
| kNN | 0.149 | 0.646 | 0.926 |
| Neural Network | 0.223 | 0.475 | 0.960 |

The Neural Network achieved the best overall performance.

---

## Example Prediction

Example article:

- Paper Age: 2 years
- Authors: 6
- References: 30
- Keywords: 10
- Venue: NeurIPS
- Title Length: 10 words
- Abstract Length: 180 words

Predicted Citation Count:

- kNN → **18 citations**
- Neural Network → **31 citations**

---

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- PyTorch
- Matplotlib

---

## Project Structure

```
Citation-Prediction/
│
├── README.md
├── project.ipynb
├── requirements.txt
├── dataset/
└── figures/
```

---

## Installation

Clone the repository:

```bash
git clone https://github.com/your-username/Citation-Prediction.git
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Run the Jupyter Notebook:

```bash
jupyter notebook
```

Open:

```
project.ipynb
```

---

## Future Work

- Use larger scientific datasets
- Include author h-index
- Include journal impact factor
- Compare with Random Forest and XGBoost
- Apply Transformer models (SciBERT)
- Develop a web application for citation prediction

---

## Author

**Lilia Beglaryan**

2026
