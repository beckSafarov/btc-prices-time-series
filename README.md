This analysis explores historical price trends of bitcoin,as well as discussing the potential factors influencing its value, and potential future outlooks. All in all,using Python libraries and Tableau for visualization, the following questions are addressed:

1. What kind of components exist in the data such as seasonality, cyclic behavior, and/or a trend?

3. What forecasting models are best to use to make future predictions?

5. Are the forecasts which were made from the chosen model logical and are based on the existing components of the time series?

The original dataset was published by bitcoincharts.com, and was obtained from kaggle.com through the following link:

https://www.kaggle.com/datasets/kognitron/zielaks-bitcoin-historical-data-wo-nan

# Major Analytical Findings



The main columns of the dataset include date, closing and opening prices of bitcoin for a day, volume of bitcoin transacted in a window and the volume weighted average price.

The following were some of the basic insights gained from the dataset as depicted in the illustrations from Tableau.

On a weekly basis, the standard deviation of the closing price fluctuates. While looking at the yearly distribution there can be observed a general trend, signaling an increased volatility compared to the early records.


![](https://web-api.textin.com/ocr_image/external/75fae24c0f968a0b.jpg)


![](https://web-api.textin.com/ocr_image/external/d127e73d36f8752d.jpg)

Figure 1 and 2. Weekly and Yearly standard deviation of the bitcoin prices

Until 2016, closing and opening prices of btc were almost the same for every day. For the next 3years, the price closed on a much smaller value than when it opened, potentially implying a fall of the btc price daily. After 2019 however, the situation changed to the opposite, when it closed with a price larger than in the opening. This in turn implied a daily growth in the btc price.


![](https://web-api.textin.com/ocr_image/external/dc9cd9fe1e1718e7.jpg)

Figure 3. Difference between closing and opening prices of bitcoin for the period

On average, there can be observed a seasonality in price as the btc price dips in April, followed by a steady growth and peak in August.


![](https://web-api.textin.com/ocr_image/external/ab6add491dc7b7d7.jpg)

Figure 4. Average Closing Price per Month

There can be observed only a partial correlation between bitcoin price and the volume of its sales.The demand is considered to be one of the main drivers of the BTC price, and as can be seen in

Figure 5, from 2016 until 2020, the volume of sales and the price rose and fell at a similar pace and volume.


![](https://web-api.textin.com/ocr_image/external/c11ecc4818093adf.jpg)

Figure 5. Correlation between price and volume

## Seasonal and Cyclical components

Looking at the general chart of the price of BTC, we can notice that there is a trend. The price started at 0 and rose up to &#36;12000. This implies that despite persistent fluctuations, bitcoin price has generally grown over the period.


![](https://web-api.textin.com/ocr_image/external/b1e5623261a16663.jpg)

Figure 6. The general chart of BTC price over the period from 2012 to 2021


![](https://web-api.textin.com/ocr_image/external/48ee7979b70f1401.jpg)


![](https://web-api.textin.com/ocr_image/external/a2cbee05af56f678.jpg)


![](https://web-api.textin.com/ocr_image/external/598fd286bc5becb2.jpg)


![](https://web-api.textin.com/ocr_image/external/7f6b17c8b0731347.jpg)


![](https://web-api.textin.com/ocr_image/external/2ea6102a1916836c.jpg)


![](https://web-api.textin.com/ocr_image/external/03fa402f5e736953.jpg)

Figure 7. Annual price change of BTC price over the period from 2012 to 2021

Looking at the price change in years from 2013 to 2018, we can observe how the trend varies year by year. This suggests that there’s no significant seasonal trend and the seasonal factors have the least effect on the price of the cryptocurrency. We can also conclude that there can be no cyclical trend as there can be observed no recurring pattern in rise and fall of the BTC value. The absence of seasonal and cyclic components imply the sheer volatility and unpredictability of the cryptocurrency.

# Random Walk Model

The first time series forecast model in the forecast section is Random Walk Model. It suggests that the value of an item is independent of the previous values but has the same distribution. Thus, it does not use the past record as the base for future forecasts. This method is considered to be simple and has a good handle of flows over complicated boundaries. However, it does not preserve the mean position of the velocity around free space. Having applied Random Walk model to this case, the mean absolute error (MAE) and the root mean square error (RMSE) were calculated to check how accurate the model is in comparison to the actual data (Figure 8):

<!-- 2025 2027 2019  -->
![](https://web-api.textin.com/ocr_image/external/16a091bca8472e0c.jpg)

Figure 8. Random Walk Model

# Moving Averages Model

According to this model, the output variables are linearly dependent on both the present and previous stochastic periods. This method's advantages include being easy to apply and interpret, removing random variables, helping identify areas of support and resistance, and offering consistent forecasts.However, this approach misses complicated relationships in the data, necessitates time histories for various time periods, and is insensitive to the seasonal and cyclical effects that occur for a purpose (Brockwell & Davis, 2016). For this model also MAE and RMSE were calculated to check its accuracy (Figure 9):

<!-- 2012  -->
![](https://web-api.textin.com/ocr_image/external/668b149910bde9e7.jpg)

Figure 9. Moving Averages Model

Holt Winter’s Exponential Smoothing

Winter's method was selected as the third forecasting model. All things considered, exponential smoothing techniques produce reliable results and are simple to use. Additionally, this technique emphasizes the importance of recent observations. But the projections that are generated are behind the real trend, and the smoothing techniques are not very good at handling trends. By using the same Python libraries, MAE and RMSE were calculated for Holt Winter’s Exponential Smoothing.


![](https://web-api.textin.com/ocr_image/external/e58fd985d4ac41f6.jpg)

Figure 10. Holt Winter’s Exponential Smoothing

## Analysis of models

All models have their mean absolute error and root mean square error compared and assessed to see which one is the best for forecasting future periods. Speaking of the differences, MAE determines the average number of errors in a series of predictions, whereas RMSE squares the errors before averaging them, giving smaller errors more weight than larger errors. Because of this, RMSE is more helpful when there are big mistakes that are undesirable. The result of all three models is depicted in the table below and Winter’s method has the smallest mean absolute error and root mean square error, which suggests that it is the most accurate:


|  | Random Walk | Moving Averages | Winter’s method |
| -- | -- | -- | -- |
| Mean absolute error | 4428.9 | 440 | 369.8 |
| Root mean squareerror | 6117.6 | 980 | 831.6 |


### Forecast

Using Winter’s method, 5, 10 and 30 months ahead of the record was forecasted. Overall the prediction was made until April of 2023. As it can be seen, the price of bitcoin is forecasted to steadily grow over the period. It’s eventually predicted to reach well over &#36;90000.


![](https://web-api.textin.com/ocr_image/external/cc79031e3a291ded.jpg)


|  |  |
| -- | -- |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |


Figure 11. Forecast of the bitcoin prices from 2020 to April 2023

### Conclusion

Data analysis is essential because it enables the drawing of inferences and the formulation of right decisions. Time series analysis on the other hand is a crucial component of the proces. However,because it relies on past data for execution, it is not always trustworthy, which presents a challenge because historical data may change over time. However, a variety of models and tools are available to compare outputs and select the model with the fewest errors.

For prediction of cryptocurrency and perhaps stock prices, Holt Winter’s exponential smoothing method is recommended due to the minimal variations in its output. By using this forecasting method bitcoin price is predicted to grow steadily (although most probably with seasonal fluctuations),continuing its upward trend and reaching new heights. Its past fluctuations, and lack of seasonal and cyclic patterns shows its high volatility, making it a highly-risky investment as a safe haven for investors.

### Bibliography

1. Davis, J. (2011). The Crypto-Currency. [online] The New Yorker. Available at:https://www.newyorker.com/magazine/2011/10/10/the-crypto-currency.

2. S, L. (2015). Who Is Satoshi Nakamoto? [online] The Economist. Available at:https://www.economist.com/the-economist-explains/2015/11/02/who-is-satoshi-nakamoto [Accessed 27 May 2024].

3. Wolff-Mann, E. (2018). ‘Only good for drug dealers’: More Nobel prize winners snub bitcoin.[online] finance.yahoo.com. Available at:

https://finance.yahoo.com/news/good-drug-dealers-nobel-prize-winners-snub-bitcoin-184903784.html?guccounter=1&guce_referrer=aHR0cHM6Ly9lbi53aWtpcGVkaWEub3JnLw&guce_ref errer_sig=AQAAAEW_aMVxEaLsQWVybSlPQ8mXqNQ0jWDGsEVmc7mOJ6WZx6NlwUWyp bT_QZab_4UwDif0CFo4G2du1Q3Be98YamFq1SiJcadhOl3y3N-2UV2-csWBaN5ctKRLH_tRjv dOexSgUr36sefgPvV6drewRNBJh1AkeK2bGZZ45fJTTuuJ [Accessed 27 May 2024].



