# A Comparative Evaluation of Time Series Forecasting Models for Glucose Prediction in Type 1 Diabetes Mellitus

- **Author:** Spyridon Mitsis
- **Degree:** BSc (Hons) Computing (Data Analytics)
- **Institution:** University of Greater Manchester
- **Thesis Supervisor:** Dr. Kyriaki-Maria Saiti
- **Date:** May 2025


## Introduction

This repository contains all the source code, experimental notebooks, and relevant materials for the BSc (Hons) Computing thesis titled "A Comparative Evaluation of Time Series Forecasting Models for Glucose Prediction in Type 1 Diabetes Mellitus." The primary objective of this research was to implement and thoroughly evaluate a diverse set of time series forecasting models for short-term blood glucose prediction in individuals with Type 1 Diabetes. The study aimed to identify promising model architectures balancing predictive accuracy, computational efficiency, and clinical safety.


## Dataset

The data used in this study was generated using the **UVA/Padova Type 1 Diabetes (T1D) Simulator (v0.2.1)**, an FDA-accepted tool for in silico testing of diabetes technologies.
*   **Citation for Simulator:** Man, Chiara Dalla et al. (Jan. 2014). “The UVA/PADOVA Type 1 Diabetes Simulator: New Features”. *Journal of diabetes science and technology* 8.1, pp. 26–34.
*   **Data Generation Script:** The specific scenarios and parameters used for data generation are based on the methodology described in (Xie et al., 2025, *Simglucose v0.2.1*).
*   **Virtual Patients:** 28 virtual patients (10 adults, 10 adolescents, 8 children).
*   **Data per Patient:** 30 days of continuous data with a 5-minute sampling interval, including:
    *   Continuous Glucose Monitoring (CGM) levels (mg/dL)
    *   Carbohydrate Intake (CHO) (grams)
    *   Bolus Insulin (U)
    *   Basal Insulin (U/hr)
*   **Data Quality:** The dataset contains no missing values.


## Models Evaluated

The following time series forecasting models were implemented and evaluated:

**Linear Models:**
*   ARIMA (Autoregressive Integrated Moving Average)
*   Exponential Smoothing (Holt-Winters Method)
*   Linear Regression
*   Naive-12 (Baseline)

**Non-linear Models (Deep Learning):**
*   LSTM (Long Short-Term Memory)
*   N-BEATS (Neural Basis Expansion Analysis for Time Series)
*   TFT (Temporal Fusion Transformer) - Standard and Tuned versions
*   Vanilla Transformer

## Software and Hardware Implementation

*   **Programming Language:** Python 3.10.12
*   **Key Libraries:**
    *   `pandas` & `numpy` for data manipulation
    *   `matplotlib` & `seaborn` for data visualization
    *   `scikit-learn` for data preprocessing (scaling, train-test split) and some models
    *   `darts` (from Unit8) for time series forecasting model implementations and evaluation
    *   `statsmodels` for ARIMA and Exponential Smoothing
    *   `pytorch` (or `tensorflow`) for deep learning models
    *   `optuna` for hyperparameter tuning
    *   `tensorboard` for experiment tracking
*   **Hardware (for training Deep Learning models):**
    *   GPU: NVIDIA GeForce RTX 4060 Laptop GPU (8GB VRAM)
    *   CPU: 13th Gen Intel(R) Core(TM) i9-13900H
    *   RAM: 32GB

## Setup and Installation

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/spyrosmitsis/glucose-prediction-t1d-comparative-study.git
    cd glucose-prediction-t1d-comparative-study
    ```

2.  **Create a virtual environment (recommended):**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows: venv\Scripts\activate
    ```

3.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```


## Results

The key findings of this comparative evaluation are detailed in the thesis document. The Transformer model demonstrated superior performance among non-linear models, achieving an MAE of 10.18 mg/dL and RMSE of 14.13 mg/dL on unseen patients, with 98.1% of predictions in clinically safe CEG Zones A/B. The ARIMA model was the best-performing linear model, establishing a strong baseline.
