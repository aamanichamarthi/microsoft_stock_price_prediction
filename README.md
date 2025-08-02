# microsoft_stock_price_prediction

This project demonstrates how to predict Microsoft (MSFT) stock closing prices using a Long Short-Term Memory (LSTM) neural network. The project utilizes historical stock data to train a deep learning model, aiming to forecast future price movements.


# Overview

Stock price prediction is a challenging task due to the volatile and non-linear nature of financial markets. This project attempts to tackle this problem by leveraging LSTM networks, a type of recurrent neural network particularly well-suited for sequence prediction tasks. The model is trained on a time series of historical Microsoft stock closing prices and then used to make predictions on unseen data.

# Dataset

The project uses historical stock data for Microsoft (MSFT),  from a CSV file named `MicrosoftStock.csv`. The dataset contains the following columns:

-   **index**: (Likely a numerical index)
-   **date**: Date of the stock record.
-   **open**: Opening price of the stock.
-   **high**: Highest price of the stock during the day.
-   **low**: Lowest price of the stock during the day.
-   **close**: Closing price of the stock.
-   **volume**: Trading volume for the day.
-   **Name**: Stock ticker (MSFT).

The notebook analyzes data from '2013-02-08' up to '2018-01-01' for prediction purposes.

## Dependencies

The project requires the following Python libraries:

-   `pandas`
-   `numpy`
-   `matplotlib`
-   `seaborn`
-   `scikit-learn`
-   `tensorflow`
-   `keras`

# Methodology
Data Loading and Initial Exploration: The MicrosoftStock.csv file is loaded into a pandas DataFrame. Basic information, descriptive statistics, and the shape of the dataset are displayed.

Data Visualization:
A plot of 'open' and 'close' prices over time is generated to visualize trends.
A plot of 'volume' over time is generated to observe trading activity.
A heatmap of the correlation matrix for numerical features is displayed to understand relationships between variables.
The closing price over the full historical period is plotted.

Data Preprocessing:

The 'close' price column is extracted for prediction.
The data is scaled using StandardScaler to normalize values, which is crucial for neural network performance.
The dataset is split into training (95%) and testing (5%) sets.
Training data is prepared for the LSTM model by creating sequences of 60 previous time steps to predict the next closing price.

LSTM Model Architecture: 
A sequential Keras model is built with the following layers:
Two LSTM layers with 64 units each. The first LSTM layer returns sequences.
A Dense layer with 128 units.
A Dropout layer with a rate of 0.5 to prevent overfitting.

A final Dense layer with 1 unit for output (the predicted closing price).

Model Compilation and Training:

The model is compiled using the 'adam' optimizer and 'mae' (Mean Absolute Error) as the loss function. RootMeanSquaredError is also used as a metric.
The model is trained for 20 epochs on the prepared training data.

Prediction: The trained model makes predictions on the unseen test set.

Visualization of Results: The actual and predicted closing prices are plotted against time to visually assess the model's performance.

License
[Specify your license here, e.g., MIT, Apache 2.0, etc.]
