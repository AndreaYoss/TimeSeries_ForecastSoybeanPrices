# Capstone - IN PROGRESS
  
##### Author: Andrea Yoss: [LinkedIn](https://www.linkedin.com/in/andreayoss/)


## Table of Contents

- [Problem Statement](#Problem-Statement)
- [Executive Summary](#Executive-Summary)
- [Datasets](#Datasets)
- [Modeling](#Modeling)
    - [Evaluation of Model](#Evaluation-of-Model)
- [Conclusion](#Conclusion)
- [Data Sources](#Data-Sources)


## Problem Statement

A commodity is essentially a raw material or agricultural product can be bought and sold.  Individual commodities are regarded as indistinguishable from other units of the same type.  Compared to stocks, commodities are quite volatile as they are based not only on prior prices, but also on external global, economic, and supply/demand factors. 

In this project, I am focusing on soybeans, and builting an unsupervised learning model that predicts future prices of this commodity.

Since the price of soybeans today are highly correlated with prior prices (i.e., lagged values of itself), I plan to conduct time series analysis on soybean prices. Further, I will identify features that have historically contributed to the volatility of soybean prices, and evaluate their predictive capabilities using the mean absolute error (MAE) as my performance metric. I will ultimately choose the model and features with the smallest MAE.  My primary stakeholders are investors in the futures market who wish to evaluate the favorability of a soybean futures contract. 
  
----

## Executive Summary

Started by conducting time series analysis on the 'Settlement Price,' or the average daily price, of soybeans from January 1, 1990 through December 31, 2019.

Next, I fit my data using an ARIMA model. 

Then, I incorporated seasonality in a SARIMA model.

Finally, I looked at introducing additional external, exogenous features in a SARIMAX model.  Some features I evaluated were: daily weather data from top US soybean producing states and seasonal US production data.  

I found that the model that did the best was my X MODEL.

----


## Datasets

|Name|Description|
|---|---|
|[S00-USA-csv.csv](/Data/S00-USA-csv.csv)| Daily Soybean commodity prices from 1/1/1990- 2/18/2020 exported from Bloomberg Terminal.|
|[NOAA_Iowa.csv](/Data/NOAA_Iowa.csv)| Daily Iowa weather data from 1/1/1990-12/31/2019 exported from the National Centers for Environmental Information (NOAA).|
|[NOAA_MN_IL.csv](/Data/NOAA_MN_IL.csv)| Daily Minnesota and Illinois weather data from 1/1/1990-12/31/2019 exported from the National Centers for Environmental Information (NOAA).|
|[USDA_Soybeans_Production.csv](/Data/USDA_Soybeans_Production.csv)| Annual US soybean production data from the United States Department of Agriculture (USDA) from 1990-2019. This dataset includes seasonal soybean approximations for: acres harvested, acres planted, and yields.|  


----

## Data Dictionaries


----

## Modeling



### Evaluation of Model

 

----

## Conclusion


----

## Limitations

**Sudden shocks based on market sentiment, and not necessarily any quantifiable features.** 
  
While I tried to account for these sudden shocks by incorporating a moving average component in my model, this only smoothed out the affects of the shocks; it does not predict them. 

I considered using natural language processing (NLP) to conduct sentiment analysis on news sources to determine likely changes in the direction of the price of soybeans. However, I decided not to include this component in my model, as any determination from this method would not only be extremely subjective, but would also quickly be reflected in the market price. With that said, an area where this could be affective would be in determining the validity of market sentiment - to determine whether or not the investor speculation that resulted in the price change is confirmed by news sentiment, for example.
  
  
**Time was a significant limitation.**
  
There are many macroeconomic factors that likely contribute to the price of soybeans; however, due to the time constraint of this project, I had to limit the number of features I analyzed.  

While the US is the largest global supplier of soybeans, Argentina and Brazil are also producers.  If I had more time to complete this project, I would've increased the scope of my project to look at global supply as a whole, not just the United States.  
  
Additionally, the strength of the United States Dollar relative to the Argentine Peso or the Brazilian Real inversely influences the price of soybeans. As the value of the US Dollar increases, the price of commododities like soybeans increase for a purchasing country based on the resultant change in the exchange rate between that country's currency and the US Dollar. Therefore, purchasing countries may choose to buy from alternative producing countries with a weaker currency, and as a result, the value of the commodity decreases as US producers are left with a greater supply vs. global demand.


----

## Next Steps



