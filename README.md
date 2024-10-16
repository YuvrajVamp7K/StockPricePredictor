# Stock Price Predictor

This project leverages **Random Forest** models to predict both the direction and magnitude of stock price changes. Using historical data from the Nifty50 index (Indian stock market), the project builds two machine learning models:

1. A **Random Forest Classifier** to predict whether the stock price will increase or decrease.
2. A **Random Forest Regressor** to predict by how much the price will increase or decrease.

## Project Structure

- **`stock_predictor.ipynb`**: 
  This notebook contains the core model training logic. It pulls historical stock data, prepares the dataset, and builds both classifier and regressor models using **Random Forest**. After training, the models are saved for future predictions.

- **`trying_the_model.ipynb`**: 
  This notebook loads the saved models and applies them to new stock data to predict both the direction and the magnitude of price changes. 

## Installation and Setup

### Requirements:
- **Python 3.x**
- **Jupyter Notebook**
- **yfinance** for stock data
- **pandas** for data manipulation
- **scikit-learn** for machine learning models
- **joblib** for saving/loading models

Install the required libraries:
```bash
pip install yfinance pandas scikit-learn joblib
```

### Running the Project:

1. **Training and testing the Model**:
   `stock_predictor.ipynb` --> This notebook pulls historical data from the Nifty50, trains a Random Forest Classifier and Regressor, and saves the models as `stockpred.pkl` and `price_change_predictor.pkl`.

2. **Use the Model**:
   Open and run `trying_the_model.ipynb`. This notebook loads the saved models and tests them on new stock data. Modify the `new_data` DataFrame in this notebook to test predictions on your own data.

## How the Models Work

- **Classifier**: 
  Predicts whether the stock price will go up or down based on features such as `Close`, `Volume`, `Open`, `High`, and `Low`.
  
- **Regressor**: 
  Predicts the magnitude of the price change (increase or decrease) based on the same features.

### Example Output:
From `trying_the_model.ipynb`:
```python
new_data = pd.DataFrame({
    'Close': [25127.95],
    'Volume': [206400],
    'Open': [25023.45],
    'High': [25159.75],
    'Low': [25017.50]
})
```
#### output
```output
Predictions for new data: [0]
the stock price will Decrease by [-62.25100365]
```
## Key Features

- **Random Forest Classifier**: Predicts price movement direction (Increase/Decrease).
- **Random Forest Regressor**: Predicts how much the price will change.
- Uses **Nifty50** stock market data for model training.
- Models are saved and reused in future predictions.

## How to Improve

- Tune the hyperparameters of the models to improve accuracy.
- Add more predictors such as moving averages or external factors like market sentiment.
- Implement a more advanced method of feature engineering to reduce RMSE in the regression model.

## Conclusion

This project provides a basic but functional model for predicting stock price movements and changes using machine learning. It's a great starting point for building more advanced financial models.
