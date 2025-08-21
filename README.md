# Gold Price Prediction Project

## Project Overview
This project focuses on predicting gold prices based on several other stock prices, including SPX (S&P 500), USO (United States Oil Fund), SLV (iShares Silver Trust), and the EUR/USD exchange rate. The goal is to build a machine learning model that can accurately forecast gold prices using historical data from these financial instruments.

## Dataset
The dataset used in this project is stored in `gld_price_data.csv` and contains the following columns:
- **Date**: The date of the observation.
- **SPX**: The closing price of the S&P 500 index.
- **GLD**: The closing price of gold (target variable).
- **USO**: The closing price of the United States Oil Fund.
- **SLV**: The closing price of the iShares Silver Trust.
- **EUR/USD**: The exchange rate between the Euro and the US Dollar.

The dataset spans from January 2008 to May 2018, with 2290 rows and 6 columns.

## Methodology

### 1. Data Loading and Exploration
- The dataset is loaded using pandas, and basic exploratory data analysis (EDA) is performed.
- Statistical summaries and correlation analysis are conducted to understand the relationships between variables.

### 2. Data Preprocessing
- The dataset is checked for missing values (none found).
- The target variable (GLD) is separated from the features (SPX, USO, SLV, EUR/USD).
- The data is split into training and testing sets (80% training, 20% testing) using `train_test_split` from scikit-learn.

### 3. Model Selection and Training
- A **Random Forest Regressor** is chosen for this prediction task due to its robustness and ability to handle non-linear relationships.
- The model is trained on the training data with 100 estimators.

### 4. Model Evaluation
- Predictions are made on the test set.
- The model's performance is evaluated using the **R-squared error** metric, which measures the proportion of variance in the target variable explained by the model.
- The achieved R-squared error is approximately **0.989**, indicating excellent predictive performance.

### 5. Visualization
- A heatmap is used to visualize the correlation between variables, showing strong positive correlation between GLD and SLV, and negative correlation with USO.
- The distribution of gold prices is plotted to understand the data's underlying structure.

## Key Insights
- **Correlation Analysis**: 
  - GLD has a strong positive correlation with SLV (0.87).
  - GLD has a weak negative correlation with USO (-0.19) and EUR/USD (-0.02).
  - SPX shows almost no correlation with GLD (0.05).
- **Model Performance**: The Random Forest model achieves an R-squared value of 0.989, demonstrating high accuracy in predicting gold prices based on the given features.

## Requirements
To run this project, you need the following Python libraries:
- `numpy`
- `pandas`
- `seaborn`
- `matplotlib`
- `scikit-learn`

Install the required libraries using:
```bash
pip install numpy pandas seaborn matplotlib scikit-learn
```

## Usage
1. Ensure the dataset `gld_price_data.csv` is in the same directory as the notebook.
2. Run the Jupyter notebook `group 5 gold price prediction.ipynb` step-by-step to reproduce the analysis and model training.
3. The notebook includes code for data loading, exploration, model training, evaluation, and visualization.

## Results
The model successfully predicts gold prices with high accuracy (R² = 0.989). The actual vs. predicted values are plotted to visually assess the model's performance, showing close alignment between the two.

