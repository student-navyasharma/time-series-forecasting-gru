# Time Series Forecasting using Custom GRU

## 📌 Overview

This project implements a complete **time series forecasting pipeline from scratch** as part of a lab assignment. The goal is to understand how sequential data is processed and how different models perform on forecasting tasks.

The implementation includes:

* MLP (baseline model)
* Custom GRU (implemented from scratch without using built-in RNN modules)
* LSTM and Transformer (for comparison)

---

## 🔢 Roll Number Based Parameters

Roll Number: **102303313**

* Window Size = 14
* Prediction Horizon = 2
* Hidden Size = 14

These parameters are derived using the formulas provided in the assignment.

---

## 📊 Datasets Used

1. **AirPassengers Dataset**

   * Monthly airline passenger counts
   * Shows clear trend and seasonality

2. **Electricity Production Dataset**

   * Time series of electricity production values
   * Contains repeating patterns and fluctuations

---

## ⚙️ Methodology

### 1. Data Preprocessing

* Extract numerical values from dataset
* Normalize data using mean and standard deviation

---

### 2. Windowing Technique

The time series is converted into supervised learning format.

* Input: past `window_size` values
* Output: next `prediction_horizon` values

Example:

```
[1,2,3,...,14] → predict [15,16]
```

---

### 3. Models Implemented

#### 🔹 MLP (Baseline)

* Takes flattened input
* Does not capture sequential dependencies

#### 🔹 Custom GRU

* Implemented manually without using `nn.GRU`
* Uses update gate and reset gate
* Maintains hidden state as memory of sequence

#### 🔹 LSTM & Transformer

* Used for comparison
* Help analyze performance differences

---

## 📈 Evaluation Metrics

* Mean Squared Error (MSE)
* Mean Absolute Error (MAE)
* Root Mean Squared Error (RMSE)

---

## 📉 Results & Observations

* GRU captures general trend but struggles with sharp peaks
* Predictions are smoother compared to actual values
* Transformer performs better due to stronger sequence modeling

---

## ❌ Failure Analysis

* Model fails to capture sudden spikes
* Predictions show lag compared to actual values
* Limited capacity leads to underfitting

---

## 🧪 Ablation Study

Model was tested with:

* Half window size
* Original window size
* Double window size

Observations:

* Smaller window → less context
* Larger window → harder training
* Optimal window → balanced performance

---

## 🧠 Conclusion

* Sequence models outperform MLP baseline
* Custom GRU demonstrates temporal learning capability
* Transformer performs best for complex patterns

---

## 🎥 Video Explanation

A detailed explanation of implementation and results is provided in the video below:

👉 https://youtu.be/3qzgZrMhKzE

---

## 🚀 How to Run

1. Open the notebook in Google Colab
2. Upload electricity dataset (`Electric_Production.csv`)
3. Run all cells sequentially

---

## 📌 Notes

* Custom GRU is implemented from scratch (no built-in sequence models used)
* Same parameters and models are applied to both datasets

---
