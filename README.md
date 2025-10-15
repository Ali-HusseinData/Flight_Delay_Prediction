# ✈️ Flight Delay Prediction

**End-to-end project (data acquisition → preprocessing → modeling → deployment)**. This repo contains a Jupyter notebook (Flight_Delay_Prediction.ipynb) that walks through data cleaning, EDA, feature engineering, model comparison and a production-friendly deployment (FastAPI + example client).

---
## Table of Contents
- [Overview](#overview)
- [Key Features](#key-features)
- [Visualizations](#visualizations)
- [Results](#results)
- [Getting Started](#getting-started)
- [Dataset](#dataset)
- [Using the API](#using-the-api)
- [Future Improvements](#future-improvements)
- [Contact](#contact)
  
---
## Overview
Flight delays affect passengers and operators alike. This project presents an end-to-end ML workflow to predict whether a flight will be delayed (binary target). It emphasizes deployment, with LightGBM recommended for production due to its efficiency and speed.

The analysis and models are implemented in the included Jupyter notebook (Flight_Delay_Prediction.ipynb).

---

## Key Features
Data cleaning & preprocessing (missing values, categorical encoding, scaling)

EDA: delay distributions and time-based patterns

Feature engineering: time features and categorical encodings

Model comparison: Logistic Regression, Random Forest, XGBoost, LightGBM

Deployment: example FastAPI app included for serving predictions

---

## Visualizations

- **Visual EDA: Feature correlations, Flights' monthly distribution**
    <img width="600" height="650" alt="image" src="https://github.com/user-attachments/assets/3619be3a-b387-427f-846d-82762ef574f4" />
    
  <img width="600" height="547" alt="image" src="https://github.com/user-attachments/assets/7d3bdcda-0d87-4f2b-93c0-d1964b84aefb" />

- **Precision-Recall Curve of RFC Model**
  
  <img width="600" height="547" alt="image" src="https://github.com/user-attachments/assets/23334d7a-3945-4de4-aeb9-b6735b2552b2" />
  
## Results
- **Random Forest (best experimental metrics)**: Accuracy ≈ **93**%, F1-score (delay) ≈ **77**%.
Note: Random Forest achieved the highest metrics in experiments but is heavy for deployment.

- **Chosen deployment model — LightGBM**: recommended for production (lighter, faster); achieved **~88% accuracy** in experiments.
  
- **Classification Report (example of Random Forest)**

```
          precision    recall  f1-score   support

       0       0.93      0.98      0.96    934555
       1       0.88      0.68      0.77    202100

accuracy                           0.93   1136655

macro avg      0.91      0.83      0.86   1136655
weighted avg   0.92      0.93      0.92   1136655 
```

Full results and plots are available inside the notebook.

---
## Getting Started
### Prerequisites
- Python 3.8+ (if running locally) or Google Colab (recommended for convenience)

- Jupyter / JupyterLab (local) or just open the notebook in Colab
### Recommended pipeline (Google Drive + Colab)
1. In Google Drive create a folder named ```Flight Delay Prediction``` (or any name you prefer). Place your dataset CSV inside that folder and name it ```flights.csv``` .

2. Typical Colab data path used by the notebook:
```
/content/drive/MyDrive/Flight Delay Prediction/flights.csv
```
4. In Colab, mount the drive at the start of the notebook:
```
from google.colab import drive
drive.mount('/content/drive')
```
4. If you have limited RAM, enable a GPU runtime (Runtime → Change runtime type → GPU) and select **T4**. This speeds up certain training steps and reduces memory pressure.

5. Clone this repo in Colab and run the notebook cells. You can edit the path for ```df``` variable in the notebook if you used a different folder name.

Why this pipeline? Mounting Drive avoids manual file uploads each session and makes the notebook quicker to start. Using Colab with T4 GPU helps users with limited local resources run heavier cells. 

---
## Dataset
The dataset used in the notebook contains flight records with fields such as:

- flight date and time

- airline

- origin and destination airports

- departure/arrival timestamps and delay status (target)

**Important:** the dataset is not included in this repository due to licensing restrictions. To reproduce the results, obtain a public dataset such as the US DOT / Kaggle "Flight Delays" or "Airline On-Time Performance" datasets and place the CSV(s) in a data/ folder, then update the notebook paths accordingly.

---
## Using the API (FastAPI)
A sample FastAPI app is included to serve the trained model. After starting the API (e.g., ```uvicorn app:app --reload```), open the auto-generated Swagger UI at ```http://localhost:8000/docs```.

To test the prediction endpoint via Swagger UI:

1. Click the ```/predict``` POST endpoint.

2. Click Try it out and paste the JSON payload below into the request body:
```
{
"month": 4,
"day": 7,
"airline": "AA",
"origin_airport": "LAX",
"destination_airport": "JFK",
"scheduled_departure": 100,
"scheduled_arrival": 1600
}
```
3. Click **Execute** to submit the request and inspect the model response.
---
## Future Improvements

- Deploy the best model as a REST API (FastAPI / Flask) for real-time predictions.

- Create a lightweight web UI (Streamlit) for user queries and visualizations.

- Integrate live flight and weather APIs to enable on-the-fly predictions.

- Experiment with time-series models and deep learning (LSTM / Transformer) for sequential dependencies.
---
## Contact
Open an issue or contact the repository owner for questions, dataset access, or collaboration.
