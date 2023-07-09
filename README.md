 
# Project 2: Gold and Bitcoin 30 day price prediction
## Background 

In this project, our goal is to predict Gold and Bitcoin (Crypto Gold) price for a 30-day testing period. The reason we chose these two types of assets is that Bitcoin is a investment opportunity, but it is very volatile and some investors don't feel comfortable investing in it. We are trying to find the entry and exit point for Bitcoin and Gold, so when Bitcoin is in decline, we will exit the position and invest the money in Gold which is much less volatile but has some potential for growth. We hope by this technique, we will increase the return of the investment and reduce the risk of investing in bitcoin and make it a more favorable investment for risk averse investors. We will be using machine learning techniques Time Series to predict the future price of Bitcoin and Gold in next 30 days and Algorithmic trading to find out entry and exit point to switch between Bitcoin and Gold.
The data for this analysis are Bitcoin and Gold historical closing prices between 1/1/2015 and 5/31/2023 which was downloaded from Yahoo Finance. We predicted the price for both between 6/1/2023 to 6/30/2023.
In our Time Series Analysis, we break the data into Training and testing and run multiple time series techniques (ARMA, ARIMA, SARIMA, SMA) to find out which technique is giving the best result for testing data so we can use it for our prediction. First, we used ARMA method, but it was giving negative Bitcoin price, so we moved to other methods to predict the future price. Between different methods we tried, ARIMA gave us the best prediction because the prediction price was closer to testing closing prices for BTC. We used the ARIMA price prediction for our next step. Later in our analysis we find the because the close prices are not stationary, we might get better results if we have used daily returns instead of closing prices. For Gold, the same trading algorithm was used but used the simple moving averages prediction data frame as ARIMA was not optimal in that case. To further optimize this model, a calculation of daily returns and tracking the simple moving averages of those results would be needed.
Same as our Time Series, for Algorithmic trading we tried different approaches to find the best results. We used (Short = 25 and long =50) and (Short = 50 and Long = 100). Shorter rolling windows did not accurately track historical closing prices; 50-100 was more accurately following the original data trend. We utilized the trading algorithms and back testing to find entry and exit points for gold and Bitcoin in the next 30 days.

## Technologies
This project leverages Python 3.7 (Jupyter Lab and VSCode) and utilizes %matplotlib inline as well as the Pandas and NumPy libraries. 
We used import datetime, prophet, yfinance, matplotlib and seaborn. 

## Installation Guide

Import pandas and numpy from the Python library

Initiate Jupyter lab from the Gitbash Terminal
used pip to install prophet, hvplot and holoviews

## Historical Price and Prediction Graphs: 
Gold and Bitcoin historical daily closing price: 
![Gold Historical daily closing price 2015-2023]("C:\Users\Afsaneh\OneDrive\Desktop\Project2\screenshots\GoldPrice2015-23.png")
![Bitcoin Historical daily closing price 2015-2023]("C:\Users\Afsaneh\OneDrive\Desktop\Project2\screenshots\BitcoinPrice2015-23.png")

We split the daily closing price to Training and testing 
![Gold Training-Testing data split]("C:\Users\Afsaneh\OneDrive\Desktop\Project2\screenshots\GoldTestTrain2015-23.png")
![BTC Training-Testing data split]("C:\Users\Afsaneh\OneDrive\Desktop\Project2\screenshots\BTCTrainTest.png")

We Pridicted closing price from 7/1/2023 to 7/30/2023 using Time series ARMA, ARIMA, SMA 
![Gold ARMA Prediction]("C:\Users\Afsaneh\OneDrive\Desktop\Project2\screenshots\GoldPredictinoARMA.png")

![Gold ARMA, ARIMA prediction]("C:\Users\Afsaneh\OneDrive\Desktop\Project2\screenshots\GoldPredictionARMA.ARIMA.png")

![Gold SMA Predition]("C:\Users\Afsaneh\OneDrive\Desktop\Project2\screenshots\GoldSMApredictions.png")

![BTC ARMA Prediction]("C:\Users\Afsaneh\OneDrive\Desktop\Project2\screenshots\BTCPredictionMARA.png")

![BTC ARMA, ARIMA prediction]("C:\Users\Afsaneh\OneDrive\Desktop\Project2\screenshots\BTCPredictionARMA-ARIMA.png")

![BTC ARIMA prediction]("C:\Users\Afsaneh\OneDrive\Desktop\Project2\screenshots\BTCARIMAprediction.png")

![BTC SMA Predition]("C:\Users\Afsaneh\OneDrive\Desktop\Project2\screenshots\BTCSMApredictions.png")

We used SMA50 and SMA100 to find entry and exit signals for Gold and Bitcoin
![Gold SMA50 SMA100 to find signals]("C:\Users\Afsaneh\OneDrive\Desktop\Project2\screenshots\GoldSMA50-100.png")

![BTC SMA50 SMA100 to find signals]("C:\Users\Afsaneh\OneDrive\Desktop\Project2\screenshots\BTCSMA50-100.png")

We used entry exit signals to predict porofile balance

![Gold entery exit siglas and portfolio value]("C:\Users\Afsaneh\OneDrive\Desktop\Project2\screenshots\GoldAlgorithm-PortfolioValue.png")

![BTC entery exit siglas and profile]("C:\Users\Afsaneh\OneDrive\Desktop\Project2\screenshots\BTCAlgorithmTOtalPortfolioValue.png")

## Conclusion:

Extend this model out further and test model using various ML techniques
Based on results no entry/exit points for testing data 
Given a portfolio value starting in 2015, there would be greater potential for returns with Bitcoin.
Historically there have been only a few instances where an entry point in BTC would indicate an exit point in Gold or vice versa. Though these assets are uncorrelated these exit and entry points are not a 1:1 tradeoff - timing the market would be difficult.
Further examination of other asset classes compared to BTC would make for better risk mitigation.


