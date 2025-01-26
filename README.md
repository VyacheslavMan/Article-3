## Benchmarking of Triple Correction method and wavelet transforms in time series forecasting: panacea or standard?  


>Authors: Manevich Vyacheslav, Ignatov Dmitry



## Abstract
This paper studies the forecasting of time series of exchange assets values and realized volatility. We take their most prominent representatives from cryptocurrencies (3 assets) and the largest participants of the S&P500, divided into 12 sets by sectors (86 assets). The paper compares a large number (above 200000) of the state-of-the-art models starting from classical (ARIMA) and machine learning (gradient boosting), different neural network architectures (CNN, LSTM, BiLSTM, CNN-LSTM, RNN, MLP, Encoder-Decoder, TabNet, Prophet) and ending with newly proposed models, TCM (Triple Correction Method) and CTCM (Corrected Triple Correction Method). The effect of wavelet transforms on the predictive power of the models is also studied in terms of MAPE, MAE and Concordance as quality metrics. It is obtained that wavelet transforms have a very positive effect on the quality of the applied models in most cases, while TCM and CTCM excel in predictive power with and without wavelet transforms. Given the number of assets and models studied and tested, the results are valid and allow us to position our work as a new benchmark.



## Content Description:

— “CTCM and TCM.ipynb” contains codes that allow full reproduction of the results obtained in the paper for the TCM and CTCM methods

— “close_frame.csv” contains input data for forecasting average daily closing price

— “rv_frame.csv” contains source data for forecasting realized volatility
