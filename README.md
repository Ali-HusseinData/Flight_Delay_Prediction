# ✈️ Flight Delay Prediction

A machine learning project to predict whether a flight will be delayed using historical flight records.

---

## Overview
Flight delays can cause inconvenience to passengers and financial losses to airlines.  
This project applies **data analysis**, **feature engineering**, and **machine learning** techniques to predict flight delays.

---

## Key Features
- **Data Cleaning & Preprocessing**: Handling missing values, encoding categorical variables, scaling numerical features
- **Exploratory Data Analysis (EDA)**: Visualizing delay trends, correlations, and patterns
- **Feature Engineering & Selection**: Extracted time-based features, encoded categorical variables (airline, origin and destination airports), and defined a binary delay flag
- **Model Training**: Testing multiple ML algorithms and tuning hyperparameters
- **Evaluation**: Accuracy, F1-score, precision, recall, and confusion matrix

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
The dataset contains:
- Flight date and time
- Airline information
- Departure & arrival airports
- Delay status (target variable)

> **Note:** The dataset used in this notebook is not included due to licensing restrictions.  
> To reproduce results, you can use a public dataset such as:  
> [US DOT Flight Delays dataset on Kaggle](https://www.kaggle.com/datasets/usdot/flight-delays).

## Future Improvements

- Integrate model into a chatbot for real-time delay queries

- Build a web app (e.g., with Flask or Streamlit)

- Use live flight + weather APIs for real-time predictions
