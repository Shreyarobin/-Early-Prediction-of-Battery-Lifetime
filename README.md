# Battery Remaining Useful Life (RUL) Prediction

Machine Learning • Stacked Ensemble • Gradio UI

Overview

This project estimates the Remaining Useful Life (RUL) of battery cells using multiple machine learning models. Each model is trained independently, and their predictions are later merged using stacked ensemble techniques to improve accuracy. A lightweight Gradio interface is included so users can interact with the final model easily and test predictions without touching the code.

Dataset Summary

Each row in the dataset reflects a snapshot of a battery at a particular moment. The goal is to predict the variable “remaining_life.”

The dataset includes:
battery_id, which uniquely identifies each cell; battery_type, describing its category; temperature, the cell temperature in Celsius; voltage, the measured voltage; max_charge, the maximum charge capacity; total_cycles, the number of complete charge–discharge cycles; charge_time, time taken to charge; discharge_time, time taken to discharge; cycle_health, a degradation measure; and remaining_life, which is the target value representing how much useful life the battery likely has left.

Models Implemented

First, several individual models are trained separately. These include K-Nearest Neighbors (KNN), Decision Tree Regressor, Random Forest Regressor, Support Vector Regressor (SVR), and a neural network built using PyTorch. Each of these models learns to estimate remaining battery life from the available features.

After training, their predictions are combined through stacked ensemble methods to improve overall performance. Three forms of ensemble are used: a weighted average, a simple average, and a stacked learning model that studies the base model outputs and learns to map them to the final prediction. This usually results in better accuracy because it captures different strengths from each model.

Evaluation

Performance is measured using R² Score and RMSE (Root Mean Squared Error). R² indicates how closely the predicted values match the actual ones, while RMSE shows the average prediction error; lower is better. In most cases, the stacked ensemble model performs better than the individual models.

How It Works (High Level)

The project begins by loading and exploring the dataset. Individual regression models are trained and tested. Their predictions are collected and fed into the ensemble layer, which produces a refined final prediction. A Gradio interface is then provided so users can input battery parameters directly and receive predicted RUL values without dealing with code.

Requirements

The project runs on Python 3.8 or higher. It uses standard scientific and machine learning libraries including pandas, numpy, scikit-learn, matplotlib, and torch. Gradio is used to build the interactive interface.
