# Early-Prediction-of-Battery-Lifetime
Battery Remaining Useful Life (RUL) Prediction

Machine Learning • Stacked Ensemble • Gradio UI

Overview

This project predicts the Remaining Useful Life (RUL) of battery cells using multiple machine learning models.
Several models are trained independently, and then their predictions are combined using stacked ensemble methods to improve accuracy.
A simple Gradio interface is included to make testing predictions easy.

Dataset Summary

Each data row represents a battery state at a moment in time.
The target output is remaining_life.

Main Columns:

battery_id — Unique battery identifier

battery_type — Category/type of battery

temperature — Battery temperature (°C)

voltage — Battery voltage (V)

max_charge — Maximum stored charge capacity

total_cycles — Number of charge-discharge cycles

charge_time — Time required to charge

discharge_time — Time required to discharge

cycle_health — Health/condition score

remaining_life — Target (Remaining Useful Life)

Models Implemented
1) Individual Models

(Each trained separately)

K-Nearest Neighbors (KNN)

Decision Tree Regressor

Random Forest Regressor

Support Vector Regressor (SVR)

Neural Network (PyTorch)

Each model attempts to estimate the battery’s remaining life based on input features.

2) Stacked Ensemble

After training individual models, their predictions are merged to form a final model.

Ensemble Techniques:

Weighted Average

Simple Average

Stacked Model (learns from base model predictions)

This boosts performance by combining the strengths of all models.

Evaluation

Models are compared using:

R² Score — Measures how well predictions match real values

RMSE (Root Mean Squared Error) — Lower is better

The stacked ensemble model generally performs the best.

How It Works (High Level)

Load and inspect dataset

Train individual regression models

Collect their predictions

Feed these predictions into an ensemble layer

Evaluate performance

Expose prediction through Gradio UI

Requirements

Python 3.8+

pandas

numpy

scikit-learn

matplotlib

torch

gradio
