# Glycemic Event Forecasting Using Continuous Glucose Monitoring Data

## Project Overview
This project aims to predict glycemic events (hypoglycemia and hyperglycemia) using continuous glucose monitoring (CGM) data. We employ machine learning techniques to forecast these events 2 hours in advance, potentially improving diabetes management and patient outcomes.

## Dataset
The dataset includes the following features:
- Time
- Blood Glucose (BG)
- Continuous Glucose Monitoring (CGM)
- Carbohydrate Intake (CHO)
- Insulin Dosage
- Low Blood Glucose Index (LBGI)
- High Blood Glucose Index (HBGI)
- Risk

## Methodology

### Feature Engineering
- Calculated 24-hour rolling averages for CGM, CHO, and insulin
- Created future CHO and insulin columns
- Generated a target variable indicating hypoglycemia (1), hyperglycemia (2), or normal (0) in the next 2 hours

### Data Split
- Split data into training and testing sets based on a specific timestamp

### Model Development
- Implemented Random Forest Classifier
- Conducted hyperparameter tuning using GridSearchCV

### Evaluation
- Assessed model performance with and without future CHO and insulin data
- Used precision, recall, F1-score, and confusion matrix for evaluation

## Results

### With Future Data

#### Initial Model
- Accuracy: 65%
- Precision: [0.74, 0.55, 0.22]
- Recall: [0.81, 0.25, 0.29]
- F1-score: [0.77, 0.34, 0.25]

#### Tuned Model
- Accuracy: 70%
- Precision: [0.74, 0.60, 0.31]
- Recall: [0.90, 0.23, 0.19]
- F1-score: [0.81, 0.33, 0.24]

### Without Future Data

#### Initial Model
- Accuracy: 63%
- Precision: [0.72, 0.51, 0.18]
- Recall: [0.81, 0.17, 0.24]
- F1-score: [0.76, 0.26, 0.20]

#### Tuned Model
- Accuracy: 68%
- Precision: [0.72, 0.59, 0.20]
- Recall: [0.90, 0.16, 0.12]
- F1-score: [0.80, 0.25, 0.15]

## Key Findings
1. Including future CHO and insulin data improves model performance.
2. Hyperparameter tuning enhances accuracy and precision for both scenarios.
3. The model performs best at predicting normal glycemic states, with challenges in accurately forecasting hypoglycemic and hyperglycemic events.

## Future Work
- Explore more advanced time series models (e.g., LSTM, Prophet)
- Incorporate additional features such as physical activity and stress levels
- Investigate techniques to improve prediction of hypoglycemic and hyperglycemic events

## Technologies Used
- Python
- Pandas for data manipulation
- Scikit-learn for machine learning models
- Matplotlib/Seaborn for data visualization (if used)


This project demonstrates the application of machine learning techniques in predicting glycemic events using continuous glucose monitoring data, potentially contributing to improved diabetes management strategies.
