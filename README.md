#  Project Overview
The project involves building a machine learning model to forecast sales based on a variety of factors, including:

- **Historical Sales:** Past performance of products across various families.  
- **External Factors:** Daily oil prices (crucial for Ecuador's economy) and local/national holiday events.  
- **Store Metadata:** Store locations, types, and clusters.  


#  Technical Stack & Tools

## Environment
- Developed in a Kaggle notebook using an NVIDIA Tesla T4 GPU to accelerate model training.

## Language
- Python 3.12  

## Core Libraries
- **pandas & numpy:** Data manipulation and processing  
- **Scikit-learn:** Label encoding and dataset splitting  
- **XGBoost:** Primary machine learning algorithm for regression  


#  Workflow Breakdown

## 1. Data Loading & Inspection
- Loaded multiple datasets:
  - train.csv  
  - test.csv  
  - oil.csv  
  - holidays_events.csv  
  - stores.csv  
  - transactions.csv  
- Training dataset contains **3M+ rows**  


## 2. Preprocessing & Feature Engineering

### Handling Missing Values
- Filled missing values in `dcoilwtico` using:
  - Forward fill (`ffill`)
  - Backward fill (`bfill`)

### Data Integration
- Merged datasets using:
  - Date  
  - Store number  

### Date Feature Extraction
Extracted features to capture seasonality:
- Day of week  
- Month  
- Year  
- Weekend indicator  


## 3. Data Encoding
- Used **LabelEncoder** to convert categorical features into numerical values:
  - family  
  - city  
  - holiday_type  


## 4. Model Training
- Model: **XGBoost Regressor**

### Configuration
- Estimators: 500  
- Learning Rate: 0.1  
- Tree Method: `hist` (optimized for large datasets)  
- Hardware: CUDA-enabled GPU  

### Performance
- RMSE improved from **1047.69 → ~332.96** on validation set  


## 5. Prediction & Submission
- Generated predictions on test data  
- Ensured no negative values:
- and exported the results to a submission.csv file for the competition.
# 6 Kaggle Competition

## Store Sales - Time Series Forecasting

🔗 Competition Link: https://www.kaggle.com/competitions/store-sales-time-series-forecasting
