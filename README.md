# HydroRiverNet Scripts

HydroRiverNet is a collection of scripts developed to process hydrological time series and apply Convolutional Neural Networks (CNNs) with subnetworks to river level prediction.  
The scripts are focused on multi-station river monitoring and enable analysis of both **flood** and **drought** patterns in the Amazon Basin.

## 🌊 Overview
The project implements a **multi-station learning approach**, where each river station contributes as an input subnetwork.  
The goal is to improve hydrological forecasting by combining signals from different locations into a unified deep learning architecture.

Included in this repository are **CSV files for all monitored stations**, covering both **flood (high-flow)** and **drought (low-flow)** years. These files are used as inputs for training and evaluation.

The workflow is divided into two main stages:
1. **Data preparation & training** – Reading CSV station files, normalizing values, creating input-output pairs, training the CNN model.  
2. **Evaluation & prediction** – Running the trained model on test years, comparing predictions with observed values, and exporting metrics.

## ⚙️ Main Scripts
- **`hydrorivernet_flood(drought).ipynb`**  
  - Loads hydrological data from multiple stations.  
  - Prepares inputs (`X`) using previous years and target outputs (`Y`) as reference years.  
  - Defines and trains a CNN with multiple subnetworks (one per station).  
  - Saves the trained model for later use.

- **`model_evaluation`**  
  - Loads the trained CNN model.  
  - Performs predictions for test datasets (e.g., 2021).  
  - Calculates error metrics:  
    - **MSE** – Mean Squared Error  
    - **MAE** – Mean Absolute Error    
    - **R²** – Coefficient of Determination  
  - Prepares outputs for visualization (time series curves, scatter plots).  

> Note: plotting scripts are separated so figures can be generated independently.

## 📂 Repository Structure
HydroRiverNet Scripts/  
│── data/  
│   ├── CSV files for all stations (flood and drought years)  
│── scripts/             # Python scripts for training & evaluation  
│   ├── hydrorivernet_flood(drought).py  
│   ├── model_evaluation  
│── outputs/             # Model checkpoints and prediction results  
│── README.md  
│── LICENSE  


