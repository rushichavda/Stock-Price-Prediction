# Final Project Explanation

This is a Prediction Model.
This Prediction Model is Made to predict future stock price based on Past data.

In This Whole file There are multiple Sections In which the Project is devided.
1) Basic Tasks
2) EDA
3) LSTM 
4) ARIMA

### Lets Take one-by-one all the sections.
**1) Basic Tasks**

Basic Tasks includes data file reading and basic Data cleaning.

**2) EDA**

EDA - Exploratory Data Analysis Included to Plot some Graphs to get the Knowledge about the dataset, patterns, trends etc.

**3) LSTM**

LSTM - Long short-term memory model is a way to make prediction from time-series data. 
I have set the task to predict next day's price using last 20-days data(i.e., 1 month in stock market).
So by that way I have reached to r2_score of ~ 0.80
The r2_Score is good but we can still optimize it with using different models

**4) ARIMA Model**

This is The Main Approch to Deal with the time-series data.

There is a Step-by-step Process to Implement ARIMA Model.

first, I am testing that the Provided Time-series Data is Stationary or not.To test that I am running ADF Test,
From the outcome of the parameters we can simply check that weather its stationary or not.
so basic mathod to do this is to check p value, It should be as low as possible(<0.5), but in our case its large.
So we have to made this data stationary.

There are multiple ways in which we can make data stationary, but here we are differencing the data and making it stationary.

To know that how many times we should perform differencing we have an tool called "ndiffs", this tool gives number of differecing required to make data stationary
so we got that number as 1.

After this I just applied auto_arima to avoid long method to get p, q values from auto co-relative graphs.
auto_arima gives best p, q, d values to minimize aic.
after getting p, q, d i input those values in arima model and i got the model learned.

Learned Model have r2_score ~ 0.95 

Then I plotted graphs to get visual idea of prediction.


