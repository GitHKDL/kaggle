# Jane Street competition 


### the competiton
1- read introduciton, understand rules and criteria
https://www.kaggle.com/c/jane-street-market-prediction

basic questions answered: https://www.kaggle.com/c/jane-street-market-prediction/discussion/198935

2- look at the data
https://www.kaggle.com/c/jane-street-market-prediction/data?select=train.csv

for ex, this EDA: https://www.kaggle.com/carlmcbrideellis/jane-street-eda-of-day-0-and-feature-importance

3- baseline model

One notebook to check to build a baseline: https://www.kaggle.com/abiolatti/jane-street-market-baseline-logistic-regression


### general intro to financial markets prediction 

https://en.wikipedia.org/wiki/Stock_market_prediction

financial market time series are highly unpredictable.

There are basically 3 school of thoughts regarding stock market prediction:
* fundamentalists: assess the quality of the company (fundamentals) in order to assess long-term profitability.

* Technical analysis: Spotting patterns in the time series of prices, using indicators based on prices and volumes. (MA, crossovers, RSI, supports, etc ...)
cf https://www.investopedia.com/terms/t/technical-analysis-of-stocks-and-trends.asp
No real science behind this, because most of it is very loosely defined. It relies mostly on assuming some "psychology" of investors in a market.

* quants: making the process as objective as possible, basing oneself on the statistical properties of time series.

Efficient market Hypothesis states that prices are a far estimate of all the future information:
P = E(Pt / It) 
There are even 3 forms of EMH; strong, medium, weak.
This relationship is true in the long-term.
Economists deduct from this that it is impossible to profit from markets. 
this is the reason why people would invest in market index such as SP500, Nikkei225, HSI, etc ...

However there is a key point to keep in mind: even if EMH is true on the long run, there is a mechanosim that makes it happen. 
Most of the theory says that there is absence of arbitrage opportunity.
for this to happen, there must be arbitrage going on ! 


Machine learning and finance: Marcos lopez de prado http://www.quantresearch.org/Lectures.htm


