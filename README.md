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
- **Feature Engineering**: Extracting time-based features
- **Model Training**: Testing multiple ML algorithms and tuning hyperparameters
- **Evaluation**: Accuracy, F1-score, precision, recall, and confusion matrix

---

## Results & Visualizations

- **Visual EDA: Delay distributions, feature correlations**

- **Confusion Matrix & Classification Report**

- **Precision-Recall Curve**

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
