# High frequency trading

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

More details, including descriptions of algorithms you can find in the notebook. The .pdf contains a short review of the suggested articles.
