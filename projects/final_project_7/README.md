# Project 7: Forecasting Electricity Load with Time-Based Fourier Features

## Overview
This project predicts household electricity consumption using only calendar
time encoded as Fourier (sine/cosine) features. We explore how well electricity
demand can be predicted directly from time without using any past consumption
data. We compare a linear approach (OLS and Ridge regression) with a nonlinear
approach (shallow neural network).

## Dataset
UCI Individual Household Electric Power Consumption (2006–2010).
Minute-level electricity readings from a single household, resampled to hourly.

Download from:
https://archive.ics.uci.edu/ml/datasets/individual+household+electric+power+consumption

## Requirements
Install dependencies:
```bash
pip install numpy pandas matplotlib scikit-learn
```
The `courselib` package is part of the course repository and is already available
at the repo root. No additional installation needed.

**1. Linear Regression**
- Builds Fourier features from hour, day of week, day of year
- Trains OLS and Ridge regression
- Experiments with K = 1, 3, 5, 10 frequency components
- Produces plots: basis functions, predictions vs actual, residuals, RMSE vs K

**2. Shallow Neural Network**
- Uses same Fourier features as input
- Trains a shallow MLP (input → 64 → 32 → 1) with ReLU activations
- Produces plots: training loss curve, predictions vs actual, residuals

## Results Summary

### Linear Models (K=5, hour + week + year features)
| Model | RMSE   | MAE    |
|-------|--------|--------|
| OLS   | 0.6396 | 0.4902 |
| Ridge | 0.6396 | 0.4902 |

OLS and Ridge perform identically at K=5, indicating no overfitting at this
frequency level. Increasing K from 1 to 10 improves RMSE from 0.727 to 0.670,
with gains plateauing after K=5.

### Neural Network (500 epochs, lr=0.001)
| Model          | RMSE   | MAE    |
|----------------|--------|--------|
| Neural Network | 0.8722 | 0.7025 |

### Model Comparison
| Model          | RMSE   | MAE    |
|----------------|--------|--------|
| OLS            | 0.6396 | 0.4902 |
| Ridge          | 0.6396 | 0.4902 |
| Neural Network | 0.8722 | 0.7025 |

Ridge regression outperforms the shallow neural network on this task.
This is expected: Fourier features already encode the periodic structure
linearly, leaving little advantage for nonlinear modeling. The neural
network may improve with more epochs or hyperparameter tuning.

## Key Findings
- Electricity consumption follows strong daily and weekly cycles
- Fourier features effectively encode these periodic patterns
- K=5 frequency components capture most of the predictable structure
- Linear models are well-suited for this periodic regression task
- The neural network captures the daily rhythm but misses sharp spikes
  caused by individual appliance usage, which time features cannot predict

## Reproducibility
All experiments run end-to-end from a single notebook each.
Random seeds are not required as linear models are deterministic.
For the neural network, results may vary slightly between runs due to
random weight initialization.