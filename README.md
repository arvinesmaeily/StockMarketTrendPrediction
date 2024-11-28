# StockMarketTrendPrediction

Predicting the trend of a stock on the Iranian Stock Exchange

## Data

Data

The data received from the tsetmc site by the pytse_client library is in the form of a csv file and its columns are as follows:

1- Date: It is the date of each record. Records are collected daily and at the end of the market.

2- Share opening price: The opening price of the share at the beginning of the market

3- The highest share trading price: The most expensive share trading day

4- The lowest share trading price: The cheapest share trading day

5- The equilibrium closing price of the share: This price is the closing price of the share after the capital increase.

6- Share trading value: The value of all share transactions made per day

7- Share trading volume: The volume of all share transactions made per day

8- Number of share transactions: The number of share transactions made per day

9- Share closing price: The closing price of the share at the end of the market

Data records are collected for each trading day (except Thursdays and Fridays and official holidays), and on days when the share is closed, the record recorded is the same as the previous day. All data received by the program (for the desired share) is saved as a csv file in the tickers_data folder in the program folder, and each time a request for new data is made, it deletes the old data and records the newer data.

## Implementation and Operation

In general, the program consists of 4 parts: data acquisition, preprocessing, training and evaluation, and prediction.

1- Data acquisition
The data is received, saved in a folder, then read and saved in a field
2- Preprocessing
The read data is first scaled and then frames of the same size are created using a sliding window to be used in the neural network.
3- Training and evaluation
In this section, two sequential models with LSTM and GRU layers are used for training. Since these layers are the best types of recurrent neural network (RNN) layers, these types of networks are the most common types of neural networks for predicting stock price trends. Therefore, these two models are used in the program. The evaluation section also examines the performance of the models on test data.
4- Forecasting
The program predicts the price change trend by generating future data (for a given number of days) and making predictions using models, recording these predictions, and comparing the predicted prices with the last price of the last actual transaction.
