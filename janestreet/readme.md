# Jane Street Kaggle competition 


### the competiton
1- read introduciton, understand rules and criteria
https://www.kaggle.com/c/jane-street-market-prediction

##### explanation on the evaluation "utility function"

![evaluation]("https://github.com/GitHKDL/kaggle/edit/main/janestreet/Image 03-01-2021 at 3.01 PM.jpg")

The final figure is terms 3 x terms 4 

Term 1 is straightforward to understand: we need to find the action(i,j) for the trade j at date i.
the consequence of choosing action = 1 is to provide the profit resp(i,j) * weight(i,j) to the total profit of date i:pi.

Hence the term 4 in the final function is just the sum over the 500 dates of the daily profit pi. 

If the evaluation function had only this term 4, then we could win the competition by being "lucky" : just find a trade that is massively profitable (or massively risky) and just trade this one. with some luck, we get a good score.

That is not what Jane street wants.

To be called a strategy, the returns should be positive and steady. 

That's why we have the term 3 in the evaluation function.
This term is basically a return (sum of all profits) divided by something like their variance.
The Variance (or volatility) is similar to risk; if a strategy provides a 1% return on average (expectation) but does it with a 10% volatility, this is a very risky deal. the ratio 1%/10% is called a Sharpe ratio; it's the return weighted by risk. In that case it is the term 2.
This term is here to penalize the profit made (term 4) by the risk taken (sharpe ratio) 

the term


basic questions answered: https://www.kaggle.com/c/jane-street-market-prediction/discussion/198935

2- look at the data
https://www.kaggle.com/c/jane-street-market-prediction/data?select=train.csv

for ex, this EDA: https://www.kaggle.com/carlmcbrideellis/jane-street-eda-of-day-0-and-feature-importance


3- baseline model

One notebook to check to build a baseline: https://www.kaggle.com/abiolatti/jane-street-market-baseline-logistic-regression
or https://www.kaggle.com/lucasmorin/running-algos-fe-for-fast-inference


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


