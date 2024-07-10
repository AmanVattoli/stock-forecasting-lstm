# Stock Forecasting using LSTM

This project focuses on predicting stock prices using a Long Short-Term Memory (LSTM) neural network.

## Steps Taken

### Data Collection
For demonstration, with a sample dataset, I used the Microsoft stock dataset from Yahoo Finance website.

### Data Preprocessing
- Filtered the dataset to include only the 'Date' and 'Close' columns.
- Converted the 'Date' column to datetime format.
- Visualized the closing prices over time using Matplotlib.
- Created a shifted dataframe to include previous time steps as features for LSTM input.
- Normalized the data using MinMaxScaler to scale the stock prices between -1 and 1.

### Feature Engineering
- Converted the dataframe to a NumPy array for further processing.
- Split the data into training and testing sets (95% training, 5% testing).

### Model Building
- Defined an LSTM model using PyTorch with one LSTM layer and a fully connected layer.
- Configured the model with appropriate input size, hidden size, and number of layers.

### Training
- Prepared the data for training by reshaping it into the required format for LSTM.
- Created PyTorch datasets and dataloaders for batching the training and testing data.
- Defined the loss function (Mean Squared Error) and the optimizer (Adam).
- Trained the model for 10 epochs, printing the training and validation loss after each epoch.

### Evaluation
- Evaluated the model’s performance on the testing data by computing the validation loss.
- Visualized the actual vs. predicted stock prices for both training and testing data.

### Prediction
- Used the trained model to make future stock price predictions.
- Visualized the predicted stock prices alongside the actual prices to demonstrate the model’s forecasting ability.

## Results

The model was able to predict stock prices with reasonable accuracy. Below is the plot showing the comparison between the actual closing prices and the predicted closing prices over time.

### Analysis

- **Trend Capture**: The LSTM model successfully captured the overall upward trend of the stock prices. This indicates that the model can effectively learn and predict long-term trends in the stock market data.
- **Short-term Variations**: The model's predictions closely follow the short-term variations in the actual stock prices, especially in the earlier part of the dataset. However, as we move towards the later part of the dataset, there is a noticeable divergence between the actual and predicted values.
- **Prediction Lag**: The predicted values tend to lag slightly behind the actual values, which is a common characteristic in time-series forecasting models. This lag can be attributed to the model's reliance on previous time steps to make predictions.
