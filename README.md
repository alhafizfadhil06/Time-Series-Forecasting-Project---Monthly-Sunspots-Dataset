# Time Series Forecasting Project - Monthly Sunspots Dataset
This repository contains the implementation of a time series forecasting model using Bidirectional LSTM. The model is trained on a dataset containing 2820 monthly susnpots data from January 1749 to December 1983. The dataset is split into a training set of 2256 data points and a validation set of 564 data points, with a train-test ratio of 80:20.

Before training the model, we first visualize the dataset to gain insights into the patterns and trends in the data. The visualization reveals that the dataset exhibits a cyclical/seasonal pattern.

We then check the stationary of the data using the Augmented Dickey-Fuller Test. This test helps us to determine whether the data is stationary, which is a key assumption for many time series forecasting models. The test reveals that the data is stationary, so we do not need to apply data preprocessing techniques to make it stationary.

To prepare the dataset for training, we apply data preprocessing techniques such as normalization using minmax scaler, splitting the dataset into windows of size 7, and creating a dataset that can be processed by the model. These techniques help to ensure that the input data is of a consistent format and is suitable for use with the model.

The main component of the model architecture is the Bidirectional LSTM layer. This layer is a type of recurrent neural network that can capture both the past and future context of the input data, which is especially useful for time series forecasting. By using Bidirectional LSTM, the model can learn to predict the future values of the time series based on the past values.

To compile the model, we use the Huber loss function, which is less sensitive to outliers compared to other loss functions. We use Adam as the optimizer with a learning rate of 0.001 and MAE as the evaluation metric. The use of MAE as the metric is useful because it provides a clear interpretation of the error magnitude in the original data units.

To avoid overfitting and improve the accuracy of the model, we apply early stopping with a stop condition based on the MAE of the training data. Specifically, training is stopped when the MAE of the training data is smaller than 5% of the data range.

Finally, we visualize the forecasting results using the validation dataset. The visualization demonstrates that the model can accurately predict the cyclical pattern and upward trend in the time series data.
