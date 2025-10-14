# ✈️ Flight Delay Prediction

A machine learning project to predict whether a flight will be delayed using historical flight records.

---

## Overview
Flight delays affect passengers and operators alike. This project demonstrates a data-science workflow — from cleaning and exploratory analysis to feature engineering, model training, and evaluation — to predict whether a flight will be delayed (binary target).

The analysis and models are implemented in the included Jupyter notebook (Flight_Delay_Prediction.ipynb).

---

## Key Features
**Data cleaning & preprocessing:** handling missing values, encoding categorical variables, scaling numeric features.

**Exploratory data analysis (EDA):** visualizations for delay distributions, time-based patterns and correlations.

**Feature engineering & selection:** extracted time-related features and encoded airline / airport categorical variables; binary delay flag defined as the target.

**Model training:** experimented with multiple ML algorithms, performed hyperparameter tuning and 

**Evaluation:** reported accuracy, precision, recall, F1-score and confusion matrices; plotted precision-recall curves.

---

## Results & Visualizations

- **Visual EDA: Delay distributions, feature correlations**

  <img width="833" height="701" alt="image" src="https://github.com/user-attachments/assets/6a7a0c19-1c47-4ae5-9d11-3b6e4442c017" />
  <img width="1112" height="1179" alt="image" src="https://github.com/user-attachments/assets/3619be3a-b387-427f-846d-82762ef574f4" />


- **Confusion Matrix & Classification Report**
<img width="683" height="547" alt="image" src="https://github.com/user-attachments/assets/262006b2-231b-4ba5-9d7d-54da6331b0e4" />


```
          precision    recall  f1-score   support

       0       0.93      0.98      0.96    934555
       1       0.88      0.68      0.77    202100

accuracy                           0.93   1136655

macro avg      0.91      0.83      0.86   1136655
weighted avg   0.92      0.93      0.92   1136655 
```

- **Precision-Recall Curve**
  
  <img width="691" height="547" alt="image" src="https://github.com/user-attachments/assets/23334d7a-3945-4de4-aeb9-b6735b2552b2" />


- Best model was **Random Forest** achieving:
  
    **Accuracy:** 93%
  
    **F1-score:** 77%

Full results and plots are available inside the notebook.

---
## Dataset
The dataset used in the notebook contains flight records with fields such as:

- flight date and time

- airline

- origin and destination airports

- departure/arrival timestamps and delay status (target)

**Important:** the dataset is not included in this repository due to licensing restrictions. To reproduce the results, obtain a public dataset such as the US DOT / Kaggle "Flight Delays" or "Airline On-Time Performance" datasets and place the CSV(s) in a data/ folder, then update the notebook paths accordingly.

Suggested dataset path used by the notebook:

```text
./data/flights.csv
```
---
## Reproducibility Notes

- Heavy preprocessing / model training can be resource-intensive; consider running on a machine with sufficient RAM or subsample the dataset for exploratory work.

- If using SMOTE or other resampling techniques, be careful to apply them only to the training split to avoid data leakage.
---
## Future Improvements

- Deploy the best model as a REST API (FastAPI / Flask) for real-time predictions.

- Create a lightweight web UI (Streamlit) for user queries and visualizations.

- Integrate live flight and weather APIs to enable on-the-fly predictions.

- Experiment with time-series models and deep learning (LSTM / Transformer) for sequential dependencies.
