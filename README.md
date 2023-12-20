# Feature engineering from financial data
This part of the project was inspired mainly by 2 articles:[Ntakaris A., Mirone G., 2019](https://www.pure.ed.ac.uk/ws/files/219083961/NtakarisEtal2019IEEEAFeatureEngineering.pdf) and [Ntakaris A., Kanniainen J., 2019](https://arxiv.org/abs/1907.09452). It is dedicated to usefull feature extraction for predicting mean price on high frequency time series.

The task was to predict price change direction using feature engineering and simple classification models. The final score is quite impressive - 0.99 accuracy and 0.99 ROC-AUC on test data.

Datasets are the following (you fing them [here](https://drive.google.com/drive/u/0/folders/1tGBEx9CEVStMKTiSkvh0Q6n5ZiLGXalf):
- `book.csv` - limit order book for perpetual bitcoin futures
- `book.spot.csv` - the same for spot bitcoin contracts
- `ticker.csv` - best prices and amounts on perp futures, have more frequent period than books
- `ticket.spot.csv` - the same for spot contracts
- `trades.csv` - file with trades at each time
- `trades.spot.csv` - same for spots
- `target1.csv` - file containing category variable (-1 - price decreased, 0 - price does not change, 1 - price rose) 

*Features which were implemented*:
- log returns
- autocorrelation with lag = 1
- realised variance
- realised bipower variance
- jump variation
- weighted mean price
- bid-ask spread
- normalized bid-ask spread

In `Feature extraction and classification.ipybn` you can find detailed results and code of implementation. 

# Implementing strategy

This project was created as a result of entrance tests in Center of Mathematical Finance. The task was to implement algorithm from (M. Avellaneda, S. Stoikov, 2006), enhance it with ideas from (A. Cartea, R. Donnely, S. Jaimungal, 2018) and test with real limit order book. In terms of impoving algorithm, I suggested heuristics that boosted total profit significantly. Here is a table of final tests: 
|Strategy\Data                    | train data | test data |
|--------------------|------------|-----------|
| naive              | -3613.79   | -19070.59 |
| inventory          | -4.22      | -44.01     |
| symmetric          | **370.12**     | **192.58**   |
| inventory enhanced | -4886.69   | -3948.38  |
| symmetric enhanced | **15139.79**   | -32891.15 |
| symmetric enhanced (1) | **824.36**   | **799.04** |
| symmetric enhanced (2) | **760.08**   | **1548.78** |
| inventory enhanced (1) | **824.42**   | **799.09** |
| inventory enhanced (2)| **421.92**   | **798.75** |

More details, including descriptions of algorithms you can find in the `.ipybn`. The `.pdf` contains a short review of the suggested articles. The data is available [here](https://drive.google.com/drive/folders/1nWvJAfUMclZpvzQ2xyfozDk8efn85RWT).

