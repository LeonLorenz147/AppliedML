# Project 7: Forecasting Electricity Load with Fourier Features

## Overview
We predict household electricity consumption using only calendar time,
encoded as Fourier (sine/cosine) features. We compare OLS and Ridge
regression across different numbers of frequency components K.

## Dataset
UCI Individual Household Electric Power Consumption (2006–2010).
Download from: https://archive.ics.uci.edu/ml/datasets/individual+household+electric+power+consumption
Place the file at: projects/final_project_7/notebooks/household_power_consumption.txt

## Requirements
pip install -r requirements.txt

## How to run
1. Open notebooks/Linear_Regression.ipynb
2. Run all cells top to bottom

## Results summary
| Model | RMSE   | MAE    |
|-------|--------|--------|
| OLS   | 0.6396 | 0.4902 |
| Ridge | 0.6396 | 0.4902 |

OLS and Ridge perform identically at K=5, indicating no overfitting
at this frequency level. Increasing K from 1 to 10 improves RMSE
from 0.727 to 0.670, with gains plateauing after K=5.