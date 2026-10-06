# Comparative Analysis of LSTM and GRU Architectures for Temperature Forecasting

## 📌 Project Overview

This project presents a comprehensive comparative analysis of two widely used Recurrent Neural Network (RNN) architectures — **Long Short-Term Memory (LSTM)** and **Gated Recurrent Unit (GRU)** — for multivariate time-series forecasting.

The study uses the **Daily Delhi Climate Time Series Dataset** to forecast daily mean temperature (`meantemp`) using historical temperature, humidity, wind speed, and atmospheric pressure observations.

The primary objective is to evaluate the two architectures from both **predictive performance** and **computational efficiency** perspectives. In addition to conventional model evaluation, the project includes training-history analysis, prediction-error analysis, feature-importance analysis, statistical comparison, and a 30-day future forecasting experiment.

The results demonstrate that the **GRU model outperformed the LSTM model on the test set while using substantially fewer parameters**, making GRU a strong candidate when both predictive performance and computational efficiency are important.

---

## 🎯 Objectives

The main objectives of this project are to:

- Analyze the Daily Delhi Climate time-series dataset.
- Perform exploratory and temporal data analysis.
- Forecast daily mean temperature using historical climate observations.
- Implement an LSTM-based time-series forecasting model.
- Implement a GRU-based time-series forecasting model.
- Compare LSTM and GRU predictive performance.
- Analyze model errors and prediction behavior.
- Compare model parameter efficiency.
- Investigate feature importance using a perturbation-based approach.
- Generate future temperature forecasts.
- Identify the more suitable architecture for this forecasting task.

---

## 📊 Dataset

The project uses the **Daily Delhi Climate Time Series Dataset**.

The dataset contains daily climate observations with the following variables:

| Feature | Description |
|---|---|
| `date` | Date of observation |
| `meantemp` | Mean temperature |
| `humidity` | Humidity |
| `wind_speed` | Wind speed |
| `meanpressure` | Mean atmospheric pressure |

The combined dataset contains approximately **1,576 observations** covering the period from **2013-01-01 to 2017-04-24**.

No missing values were identified during the initial data-quality assessment.

> **Data-quality note:** The exploratory analysis identified unusually large and negative values in `meanpressure`. The notebook reports this issue but proceeds with the modeling workflow without a dedicated outlier-treatment step.

---

## 🔍 Exploratory Data Analysis

The project performs comprehensive exploratory analysis of the climate variables, including:

- Temperature trends over time
- Temperature distribution
- Humidity trends and distribution
- Wind-speed trends and distribution
- Atmospheric-pressure trends and distribution
- Feature correlation analysis
- Monthly temperature patterns
- Yearly temperature trends
- Seasonal temperature distributions

Temporal features are also derived from the date variable, including:

- Year
- Month
- Day
- Day of year
- Quarter
- Season

---

# 🧠 Methodology

The complete workflow follows these stages:

```text
Daily Delhi Climate Dataset
            │
            ▼
    Data Loading & Validation
            │
            ▼
 Exploratory Data Analysis
            │
            ▼
   Temporal Feature Analysis
            │
            ▼
 Feature Selection & Scaling
            │
            ▼
  60-Day Sequence Generation
            │
            ▼
       Train / Validation / Test
            │
       ┌────┴────┐
       ▼         ▼
     LSTM       GRU
       │         │
       └────┬────┘
            ▼
      Model Training
            │
            ▼
    Test-Set Evaluation
            │
            ▼
 Comparative Analysis
            │
       ┌────┼────────────┐
       ▼    ▼            ▼
   Errors  Feature    Future
  Analysis Importance Forecast
## Disclaimer

This project is developed for academic and research purposes. Forecasting performance is specific to the dataset, preprocessing pipeline, model architectures, and experimental configuration used in this study.
