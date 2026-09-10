# Regression - Yes Bank Stock Closing Price Prediction

## Project Overview

This project focuses on predicting Yes Bank's monthly closing stock price using machine learning regression techniques. Historical stock-price data is analyzed to identify patterns and relationships between Open, High, and Low prices and the Closing price.

The project includes data preprocessing, exploratory data analysis, hypothesis testing, feature selection, machine learning model development, hyperparameter tuning, model evaluation, and model deployment preparation.

## Business Objective

To build a machine learning regression model that predicts Yes Bank's monthly closing stock price using historical stock-price data.

## Dataset

The dataset contains 185 records and 5 columns:

- **Date** - Monthly stock-price record
- **Open** - Opening stock price
- **High** - Highest stock price during the month
- **Low** - Lowest stock price during the month
- **Close** - Closing stock price and target variable

The dataset contains no missing values or duplicate records.

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- SciPy
- SHAP
- Joblib
- Jupyter Notebook

## Project Workflow

1. Data Loading
2. Data Preprocessing
3. Exploratory Data Analysis
4. Hypothesis Testing
5. Feature Manipulation and Selection
6. Data Transformation and Scaling
7. Data Splitting
8. Machine Learning Model Development
9. Cross-Validation and Hyperparameter Tuning
10. Model Evaluation
11. Model Explainability
12. Model Saving and Prediction on Unseen Data

## Exploratory Data Analysis

The following analyses and visualizations were performed:

- Monthly Closing Price Trend
- Monthly Opening vs Closing Price Difference
- Distribution of Closing Price
- Open Price vs Closing Price
- High Price vs Closing Price
- Open Price Distribution
- High Price Distribution and Outliers
- Low Price Distribution
- Monthly Price Range
- Monthly Closing Price Change
- Average Closing Price by Year
- Low Price vs Closing Price
- Closing Price with Rolling Average
- Correlation Heatmap
- Pair Plot

## Hypothesis Testing

Three hypotheses were tested:

### 1. Open Price vs Close Price

Pearson Correlation Test was used to determine whether there is a significant relationship between Open and Close prices.

### 2. Average Closing Price Across Years

One-Way ANOVA was used to determine whether the average closing price differs significantly across different years.

### 3. Average Monthly Return

A One-Sample t-test was used to determine whether the average monthly return is significantly different from zero.

## Machine Learning Models

### Model 1 - Linear Regression

Linear Regression was used as the baseline regression model.

**R² Score:** 0.9848

GridSearchCV with TimeSeriesSplit was used for hyperparameter optimization. The tuned model did not show improvement over the original model.

### Model 2 - Random Forest Regression

Random Forest Regression was used as an ensemble learning approach.

**R² Score:** 0.9719

GridSearchCV with TimeSeriesSplit was used for hyperparameter tuning. The original Random Forest model performed slightly better than the tuned model on the test data.

### Model 3 - Gradient Boosting Regression

Gradient Boosting Regression was used as another ensemble learning approach.

The tuned Gradient Boosting model achieved:

- **MAE:** 13.02
- **MSE:** 554.75
- **RMSE:** 23.55
- **R²:** 0.9662

After hyperparameter tuning, the model showed improvement compared with the original Gradient Boosting model.

## Final Model

The **Tuned Gradient Boosting Regression model** was selected as the final prediction model based on its improved performance after hyperparameter tuning and its strong predictive capability.

The model was trained using:

- Open
- High
- Low

as input features and:

- Close

as the target variable.

## Model Explainability

SHAP (SHapley Additive exPlanations) was used to understand feature importance and explain the contribution of the input features to the model's predictions.

## Model Saving

The final trained model was saved using Joblib:

`yes_bank_gradient_boosting_model.joblib`

The saved model was loaded again and tested on unseen data to perform a sanity check.

## Key Findings

- Open, High, and Low prices have strong positive relationships with the Close price.
- Yes Bank's closing price showed significant fluctuations over time.
- Several periods showed high price volatility.
- The tuned Gradient Boosting model improved its performance after hyperparameter tuning.
- The final model achieved an R² score of 0.9662.

## Business Impact

The model can support financial analysis, stock-price trend assessment, risk evaluation, and data-driven decision-making by providing estimated closing prices based on historical stock-price information.

However, stock prices are affected by various external factors such as market conditions, economic events, and investor sentiment. Therefore, model predictions should be considered as analytical support and not as a guarantee of future stock performance.

## Future Scope

Future improvements can include incorporating additional variables such as trading volume, market indicators, and broader market trends. Advanced time-series models such as ARIMA, SARIMA, and LSTM can also be explored to capture temporal patterns and potentially improve forecasting performance.

## Project Files

- `Yes_Bank_Stock_Price_Prediction.ipynb` - Complete project notebook
- `data_YesBank_StockPrices.csv` - Dataset
- `yes_bank_gradient_boosting_model.joblib` - Saved final ML model
- `requirements.txt` - Required Python libraries

## Conclusion

This project demonstrates the application of machine learning regression techniques for predicting Yes Bank's monthly closing stock price. After comparing multiple regression models and applying hyperparameter tuning, the tuned Gradient Boosting Regression model was selected as the final model. The model achieved an R² score of 0.9662 and was successfully saved and tested on unseen data.
