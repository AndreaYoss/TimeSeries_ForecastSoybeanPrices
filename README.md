# Capstone
  
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

Since the price of soybeans today are highly correlated with prior prices (lagged values of itself), I plan to conduct time series analysis on soybean prices. Further, I will identify features that have historically contributed to the volatility of soybean prices, and evaluate their predictive capabilities using the mean absolute error (MAE) as my performance metric. I will ultimately choose the model and features with the smallest MAE.  My primary stakeholders are investors in the futures market who wish to evaluate the favorability of a soybean futures contract. 
  
----

## Executive Summary


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

----

## Next Steps


