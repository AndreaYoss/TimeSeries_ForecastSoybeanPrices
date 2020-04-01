# Capstone Project: Forecasting Soybean Prices Using Time Series Analysis
  
#### Author: Andrea Yoss: [LinkedIn](https://www.linkedin.com/in/andreayoss/)


## Table of Contents

- [Problem Statement](#Problem-Statement)
- [Executive Summary](#Executive-Summary)
- [Datasets](#Datasets)
- [Analysis](#Analysis)
- [Conclusion](#Conclusion)
- [Data Sources](#Data-Sources)


## Problem Statement

A commodity is essentially a raw material or agricultural product that can be bought and sold.  Individual commodities are regarded as indistinguishable from other units of the same type, and can be bought and sold on commodities markets using futures.  A futures contract is  an agreement between a buyer and a seller committing the buyer to purchasing a specific quantity of a commodity from the seller sometime in the future at a set price. 

Similar to investing in individual stocks, investors choose to enter into futures contracts when they believe they can profit from the agreement.  Specifically, they often invest in futures if they believe the actually price of the underlying commodity will differ at the time of expiration from the price agreed on in the contract, and so they expect to profit from this difference.  

Unfortunately, commodities prices are notoriously volatile.  Since these are based not only on prior prices and related supply/ demand factors, but also on a varity of macroeconomic factors, long-term prices are difficult to forecast.

In this project, I am focusing on soybeans, and building a model that predicts future prices of this commodity.

Since the price of soybeans today are highly correlated with prior prices (i.e., lagged values of itself), I plan to conduct time series analysis on soybean prices. Further, I will identify features that have historically contributed to the volatility of soybean prices, and evaluate their predictive capabilities. I will ultimately choose the model the smallest Mean Absolute Error as my evaluation metric.  My primary stakeholders are investors in the futures market who wish to evaluate the favorability of a soybean futures contract. 
  
----

## Executive Summary

Using historical daily soybean price data from from January 1, 1990 through December 31, 2019, as well as daily weather data over the same time period, I built a variety models to predict prices of soybeans.

To accomplish this, I started off conducting univariate time series analysis on just the daily average price of soybeans. During EDA, I identified the presence of certain components that I needed to account for in my model: the existance of a long-term trend, seasonality and residual components of the price data. 

After checking for stationarity using an Augmented Dickey-Fuller test, I addressed the long-term stable trends and presence of random "shocks" in the price by using the Autoregressive Integrated Moving Average model (ARIMA). I then incorporated the soybean crop seasonality into the model using an Seasonal Autoregressive Integrated Moving Average model (SARIMA).  Finally, I introduced additional external, exogenous features in my multivariate time series analysis. I built a SARIMAX model, using the minimum and maximum daily temperatures in top US soybean producing states lagged by 72 days, to the prior season; as these feature had the highest correlation with price, compared to the other weather related features I was considering.

I found that my SARIMA(4,1,4)(1,0,72) was my best model with an MAE = 0.77.  

----


## Datasets

|Name|Description|
|---|---|
|[S00-USA-csv.csv](/Data/S00-USA-csv.csv)| Daily Soybean commodity prices from 1/1/1990- 2/18/2020 exported from Bloomberg Terminal.|
|[NOAA_Iowa.csv](/Data/NOAA_Iowa.csv)| Daily Iowa weather data from 1/1/1990-12/31/2019 exported from the National Centers for Environmental Information (NOAA).|
|[NOAA_MN_IL.csv](/Data/NOAA_MN_IL.csv)| Daily Minnesota and Illinois weather data from 1/1/1990-12/31/2019 exported from the National Centers for Environmental Information (NOAA).|
 
----

## Analysis

I built and analyzed the following time series models:
  
1. Autoregressive Integrated Moving Average model (ARIMA)
2. Seasonal Autoregressive Integrated Moving Average model (SARIMA)
3. Seasonal Autoregressive Integrated Moving Average with eXogenous regressors (SARIMAX)

My results were as follows:

#### Table 1: Time Series Model Comparison

|Model|Mean Absolute Error|
|---|---|
|ARIMA(4,1,4)| 0.978|
|SARIMA(4,1,4)(1,0,72)| 0.770|
|SARIMAX(4,1,4)(1,0,72)|0.770|

My SARIMA and SARIMAX models had the same MAE, meaning that the inclusion of the exogenous feature did not have an affect on my predictive capability.  We can look at the difference between my ARIMA and SARIMA models in the figure below.


<img src="Images/predictions_ARIMA_SARIMA.png">

Note in May 2018, there was speculation of a trade war between the US and China, one of the US's largest soybean customers. As a result of this uncertainty and potential drop in demand, the market quickly responded with a drop in the price of soybeans.  A month later, in July 2018, this speculation was confirmed as China imposed a 25% import tariff on US Soybeans.  Neither of our models could have predicted this random "shock."  

----

## Conclusion

The volatility in soybean prices caused by a variety of macroeconomic factors makes it difficult to forecast long-term prices. However, by building a model that accounts for long-term trends, sudden shocks, and seasonality, I was able to use my differenced pricing data to create a model with a mean absolute error of $0.77.
  
Some limitations included:

**Sudden shocks based on market sentiment, and not necessarily any quantifiable features.** 
  
While I tried to account for these sudden shocks by incorporating a moving average component in my model, this only smoothed out the affects of the shocks; it does not predict them. 

I considered using natural language processing (NLP) to conduct sentiment analysis on news sources to determine likely changes in the direction of the price of soybeans. However, I decided not to include this component in my model, as any determination from this method would not only be extremely subjective, but would also quickly be reflected in the market price. With that said, an area where this could be effective would be in determining the validity of market sentiment - to determine whether or not the investor speculation that resulted in the price change is confirmed by news sentiment, for example.
  
  
**Time was a significant limitation.**
  
There are many macroeconomic factors that likely contribute to the price of soybeans; however, due to the time constraint of this project, I had to limit the number of features I analyzed.  

While the US is the largest global supplier of soybeans, Argentina and Brazil are also producers.  If I had more time to complete this project, I would've increased the scope of my project to look at global supply as a whole, not just the United States.  
  
Additionally, the strength of the United States Dollar relative to the Argentine Peso or the Brazilian Real inversely influences the price of soybeans. As the value of the US Dollar increases, the price of commododities like soybeans increase for a purchasing country based on the resultant change in the exchange rate between that country's currency and the US Dollar. Therefore, purchasing countries may choose to buy from alternative producing countries with a weaker currency, and as a result, the value of the commodity decreases as US producers are left with a greater supply vs. global demand.



----

## Data Sources

Bloomberg L.P. (2020) *[Historical Pricing Data for Soybeans(CBT $/bu) Continuous(S00-USA) from 1/1/1990 to 2/18/2020, CBOTCommodity.](https://github.com/AndreaYoss/Capstone/blob/master/Data/S00-USA-csv.csv)* Retrieved from Bloomberg database. (Accessed: 19 February 2020).

[National Oceanic and Atmospheric Administration (NOAA) Climate Data Online](https://www.ncdc.noaa.gov/cdo-web/).









