# Trading Analysis and Stock Price Prediction using PySpark

### Disclaimer
The stock price prediction model developed in this project is for educational and experimental purposes only. It is not intended to be used for making real-life trading or investment decisions. The creators is not responsible for any financial losses resulting from its use.


## 1. Introduction 
In an increasingly data-driven world, PySpark is a critical tool for big data analytics. This project explores PySpark's immense potential in trading (data) analysis and stock price prediction using Machine Learning techniques. A comprehensive exploratory analysis of our stock dataset is performed, where key metrics such as profitability and consistent growth of stocks is visually explored. Furthermore, technical indicators such as Moving Averages and Relative Strength Index (RSI) are incorporated to provide deeper insights into trends of the stock market and stock prices. Subsequently, data preprocessing is performed which comprises cleaning of the dataset and engineering a crucial feature, Normalized Close which serves as the target variable for predictive modeling. PySpark’s machine learning library (MLlib) is utilized for the ML needs of this project. A Random Forest Regression model is trained to predict normalized closing prices for stocks in this project’s effort to implement a robust and efficient system for analyzing large-scale stock data. Finally,  a backtesting simulation strategy is implemented which utilizes historical stock data to simulate trading decisions, offering insights into the model's real-world applicability and profitability.


## 2. Insights from Plots 

_Note: Corresponding sections of the notebook are mentioned in the following headings._

### 1.2.4 Using Moving Averages for Stock Trend Analysis

![Trend Analysis by using SMAs](https://github.com/aratrika02/stock-analysis-project/blob/main/sma_amd.png)

For the Trend Analysis plot of AMD, the following insights can be derived:

The plot depicts a mostly consistent trend except in 2014-2015.

Trends observed: 

2014-2015: A period of volatility with frequent trend changes, switching between bullish and bearish periods

2015-2016: bearish period, 

2016-2018: predominantly bullish period,

2018- : bearish period

Breaks: In 2015, there is a break (stock price crosses below SMA)  which signals the beginning of a downtrend and is in fact followed by a bearish period.
Subsequently, in the beginning of 2016, there is another break where the stock prices crosses above the SMA indicating an uptrend and is then followed by a bullish period.


### 1.2.5 RSI Analysis
For the RSI analysis of AMD stocks:

![Trend Analysis by using RSI](https://github.com/aratrika02/stock-analysis-project/blob/main/rsi_amd.png)

* Relatively stable, significant upward trend starts after 2016 but this period is illustrates a lot of volatility by the frequent price drops and rise. 
* The red triangles signal overbought conditions and many of these points are followed by price drops, confirming the overbought signal's relevance.
* Green triangles mark oversold conditions indicating a potential price rebound and is confirmed as many of the points  are followed by an upward trend.
* The RSI consistently fluctuates between 0 and 100, mostly staying within the 30–70 range, illustrating typical market conditions.
* Frequent entry into the overbought zone before 2017 suggests high bullish trend (corroborated by the Trend Analysis using SMA plot)


### 1.2.6 Combining RSI and MAs for further analysis:

![Trend Analysis by using RSI+SMA](https://github.com/aratrika02/stock-analysis-project/blob/main/sma_rsi_amd.png)

For AMD stocks: 
- Green triangle indicate the 50 day SMA crossing over the 200 day SMA indicating a bullish period (seen predominantly in 2016 in the Trend Analysis using SMAs plot).
- Red triangles highlight the 50 day SMA crossing below 200 day SM indicating the onset of a bearish period of declining stock prices.
- Buy signal is strengthened when a bullish crossover coincides with an oversold RSI.
- Sell signal is strengthened when a bearish crossover coincides with an overbought RSI.


### 4.1 Backtesting Analysis for Meta

![Backtesting Analysis of META](https://github.com/aratrika02/stock-analysis-project/blob/main/meta.png)

- The portfolio value increases consistently over the observed time period, indicating that the trading strategy is profitable overall.
- The absence of sharp declines in portfolio value suggests that the strategy effectively avoids significant losses or risks.
- The portfolio value appears to grow at an accelerating rate over time, which could be due to compounding gains as the reinvested profits amplify returns.
- Some segments of the graph show relatively flat regions, indicating periods where the strategy held positions which could be because market movements were minimal or our strategy could not capitalize on some market trends.

We start with a portfolio value of $10,000 in 2013 and end up at nearly 21 million dollars in 2023.

### 4.2 Backtesting Analysis for NVIDIA
![Backtesting Analysis of NVIDIA](https://github.com/aratrika02/stock-analysis-project/blob/main/nvidia.png)

- Significant jumps in the portfolio value, particularly noticeable in the mid-2010s, could be an indication of periods of strong market trends or highly successful predictions by the strategy.
(NVIDIA actually had one of its most profitable years in 2016 with an almost 233% increase in its stock returns [7]. This could be attributed to NVIDIA’s advancements in GPUs with applications in gaming, data centers and most importantly, AI hardware development.)
- The increasing steepness of the curve toward later years highlights the compounding effect of reinvested gains, where higher portfolio values lead to amplified returns over time.
- The consistent upward trend over two decades indicates that the predictions and trading strategy are robust across different market conditions.

We start with a portfolio value of $10,000 in 2003 and end up at nearly 30 million dollars in 2016 and 66 million dollars in 2023. 

To corroborate the immense stock returns in case of NVIDIA, the 50-day and 200-day SMAs has been plotted to identify bullish and bearish trends. The high returns of NVIDIA stocks can be corroborated by the dominant bullish periods starting from 2016. (see _4.2.1 Exploratory Data Analysis For NVIDIA_ in the notebook)
![SMA analysis of NVIDIA](https://github.com/aratrika02/stock-analysis-project/blob/main/sma_nvidia.png)



