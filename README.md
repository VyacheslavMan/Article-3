## Benchmarking of Triple Correction method and wavelet transforms in time series forecasting: panacea or standard?  


>Authors: Manevich Vyacheslav, Ignatov Dmitry



## Abstract
This paper studies the forecasting of time series of exchange assets values and realized volatility. We take their most prominent representatives from cryptocurrencies (3 assets) and the largest participants of the S&P500, divided into 12 sets by sectors (86 assets). The paper compares a large number (above 200000) of the state-of-the-art models starting from classical (ARIMA) and machine learning (gradient boosting), different neural network architectures (CNN, LSTM, BiLSTM, CNN-LSTM, RNN, MLP, Encoder-Decoder, TabNet, Prophet) and ending with newly proposed models, TCM (Triple Correction Method) and CTCM (Corrected Triple Correction Method). The effect of wavelet transforms on the predictive power of the models is also studied in terms of MAPE, MAE and Concordance as quality metrics. It is obtained that wavelet transforms have a very positive effect on the quality of the applied models in most cases, while TCM and CTCM excel in predictive power with and without wavelet transforms. Given the number of assets and models studied and tested, the results are valid and allow us to position our work as a new benchmark.


## Benchmarking

To obtain a comparative benchmark table for each type of time series under study, a visual variation of the Copeland method (Copeland A.H. (1951)) is used. The unified benchmark ranking table is constructed according to the following logic:

  1) For each asset and each error metric, the best models are identified within each examined model family, regardless of the use of wavelets: Naive, TCM, CTCM, NN, ARMA, XGBoost;

  2) Based on the selected models and their error metrics, an error-metric matrix is formed. It is represented as follows: columns correspond to assets, rows correspond to models, and at their intersection are the values of the error metric of a given model for a given asset. That is, element (i,j) is the value of a specific error metric for model i on asset j. Thus, three error-metric matrices are obtained for each data type under study;

  3) For each error-metric matrix, a count matrix is constructed that reflects how many times model i is better than model j and vice versa according to error metric e. If the error-metric value of model i is greater than the corresponding value for model j, the counter of model i is incremented by 1, and the counter of model j is incremented by 0. If the error-metric values differ by less than 1e-6, both models receive +0. Thus, element (i,j) of this matrix shows how many times model i turned out to be better than model j;

  4) To obtain the aggregate count matrix, all three count matrices for each error metric are summed according to the rules of matrix addition. As a result, one aggregate count matrix is obtained for each type of asset under study;

  5) The values in each row of the resulting aggregate count matrix are summed, yielding the total counter: how many times a particular model outperformed the other best models for this data type across all error metrics.


### Ranking table for benchmarks for ACP
|      | ARMA | CTCM | NAIV | NN  | TCM | XGBoost | Rank |
|------|------|------|------|-----|-----|---------|------|
| NAIV | 13.0 | 16.0 | 0.0  | 17.0| 15.0| 15.0    | 76.0 |
| TCM  | 8.0  | 12.0 | 4.0  | 15.0| 0.0 | 12.0    | 51.0 |
| ARMA | 0.0  | 11.0 | 6.0  | 11.0| 11.0| 10.0    | 49.0 |
| CTCM | 7.0  | 0.0  | 3.0  | 10.0| 5.0 | 6.0     | 31.0 |
| XGBoost | 6.0 | 9.0 | 3.0 | 8.0 | 5.0 | 0.0     | 31.0 |
| NN   | 6.0  | 8.0  | 2.0  | 0.0 | 4.0 | 0.0     | 20.0 |


### Ranking table for benchmarks for RV

|        | ARMA | CTCM | NAIV | NN   | TCM  | XGBoost | Rank  |
|--------|------|------|------|------|------|---------|-------|
| ARMA   | 0.0  | 75.0 | 89.0 | 49.0 | 81.0 | 71.0    | 365.0 |
| NN     | 68.0 | 60.0 | 84.0 | 0.0  | 74.0 | 42.0    | 328.0 |
| CTCM   | 36.0 | 0.0  | 64.0 | 49.0 | 56.0 | 58.0    | 263.0 |
| XGBoost| 36.0 | 42.0 | 65.0 | 36.0 | 47.0 | 0.0     | 226.0 |
| TCM    | 30.0 | 39.0 | 60.0 | 39.0 | 0.0 | 46.0    | 214.0 |
| NAIV   | 22.0 | 45.0 | 0.0  | 21.0 | 50.0 | 41.0    | 179.0 |



## Content Description:

— “CTCM and TCM.ipynb” contains codes that allow full reproduction of the results obtained in the paper for the TCM and CTCM methods

— “close_frame.csv” contains input data for forecasting average daily closing price

— “rv_frame.csv” contains source data for forecasting realized volatility


## Literature:
Copeland A.H. (1951). A reasonable social welfare function (mimeo), University
of Michigan, Ann Arbor (Seminar on Application of Mathematics to the Social
Sciences).
