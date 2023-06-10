 
# Project 2: Gold and Bitcoin 30 day price prediction

In this project, our goal is to predict Gold and Bitcoin (Crypto Gold) price for a 30-day testing period. The reason we chose these two types of assets is that Bitcoin is a investment opportunity, but it is very volatile and some investors don't feel comfortable investing in it. We are trying to find the entry and exit point for Bitcoin and Gold, so when Bitcoin is in decline, we will exit the position and invest the money in Gold which is much less volatile but has some potential for growth. We hope by this technique, we will increase the return of the investment and reduce the risk of investing in bitcoin and make it a more favorable investment for risk averse investors. We will be using machine learning techniques Time Series to predict the future price of Bitcoin and Gold in next 30 days and Algorithmic trading to find out entry and exit point to switch between Bitcoin and Gold.
The data for this analysis are Bitcoin and Gold historical closing prices between 1/1/2015 and 5/31/2023 which was downloaded from Yahoo Finance. We predicted the price for both between 6/1/2023 to 6/30/2023.
In our Time Series Analysis, we break the data into Training and testing and run multiple time series techniques (ARMA, ARIMA, SARIMA, SMA) to find out which technique is giving the best result for testing data so we can use it for our prediction. First, we used ARMA method, but it was giving negative Bitcoin price, so we moved to other methods to predict the future price. Between different methods we tried, ARIMA gave us the best prediction because the prediction price was closer to testing closing prices for BTC. We used the ARIMA price prediction for our next step. Later in our analysis we find the because the close prices are not stationary, we might get better results if we have used daily returns instead of closing prices. For Gold, the same trading algorithm was used but used the simple moving averages prediction data frame as ARIMA was not optimal in that case. To further optimize this model, a calculation of daily returns and tracking the simple moving averages of those results would be needed.
Same as our Time Series, for Algorithmic trading we tried different approaches to find the best results. We used (Short = 25 and long =50) and (Short = 50 and Long = 100). Shorter rolling windows did not accurately track historical closing prices; 50-100 was more accurately following the original data trend. We utilized the trading algorithms and back testing to find entry and exit points for gold and Bitcoin in the next 30 days.

# Install the required libraries
# Import libraries and dependencies
# Get BTC-USD ticker information
# Get closing historical prices for BTC-USD 
# Running Time series model 
# using split, Fit, Predict and test steps on Bitcoin closing price 
# specifying number of testing data
# Split data to Training and testing Data
# Fit the Model
# Predit the data and Plot the data
# Repeat same steps for all models we used

![ARMA Prediction]("Project2\scerrenshot\Screenshot 2023-06-07 113849.png")
![ARIMA Prediction]("Project2\scerrenshot\Screenshot 2023-06-07 114302.png")
![ARIMA Prediction]("Project2\scerrenshot\Screenshot 2023-06-07 114407.png")

# Used Prediction data to find entry Exit points
# Filter the date index and close columns
# Review the DataFrame
# Use hvplot to visualize the data
# Set the variables for short window and long window periods
# Generate the short and long window simple moving averages (50 and 100 days, respectively)
# Create a column to hold the trading signal
# Generate the trading signal 0 or 1,
# where 1 is the short-window (SMA50) greater than the long-window (SMA100)
# and 0 is when the condition is not met
# Calculate the points in time when the Signal value changes
# Identify trade entry (1) and exit (-1) points
# Visualize exit position relative to close price
# Show the plot
# Visualize entry position relative to close price
# Show the plot
# Visualize close price for the investment
# Show the plot
# Visualize moving averages
# Show the plot
# Create the overlay plot
# Show the plot
# Set initial capital
# Set the share size
# Buy a 100 share position when the dual moving average crossover Signal equals 1 (SMA50 is greater than SMA100)
# Sell a 100 share position when the dual moving average crossover Signal equals 0 (SMA50 is less than SMA100)
# Determine the points in time where a 500 share position is bought or sold
# Multiply the close price by the number of shares held, or the Position
# Subtract the amount of either the cost or proceeds of the trade from the initial capital invested
# Calculate the total portfolio value by adding the portfolio cash to the portfolio holdings (or investments)
# Calculate the portfolio daily returns
# Calculate the portfolio cumulative returns
# Print the DataFrame
# Visualize exit position relative to close price
# Show the plot
# Visualize entry position relative to close price
# Show the plot
# Visualize close price for the investment
# Show the plot
# Visualize moving averages
# Show the plot
# Create the overlay plot
# Show the plot
# Visualize exit position relative to total portfolio value
# Visualize entry position relative to total portfolio value
# Visualize the value of the total portfolio
# Overlay the plots
![BTC SMA 50-100  Entry - Exit ]("Project2\scerrenshot\bokeh_plot (1).png")
![BTC Algoritm Total value ]("Project2\scerrenshot\bokeh_plot (2).png")
![Gold SMA 50-100  Entry - Exit ]("Project2\scerrenshot\bokeh_plot (4).png")
![GOLD Algoritm Total value ]("Project2\scerrenshot\bokeh_plot (6).png")