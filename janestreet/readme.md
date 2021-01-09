# Jane Street Kaggle competition 


### the competiton
1- read introduciton, understand rules and criteria
https://www.kaggle.com/c/jane-street-market-prediction

##### explanation on the evaluation "utility function"

![evaluation](https://github.com/GitHKDL/kaggle/blob/main/janestreet/Image%2003-01-2021%20at%203.01%20PM.jpg)

The final figure is terms 3 x terms 4 

* Term 1 is straightforward to understand: we need to find the action(i,j) for the trade j at date i.
the consequence of choosing action = 1 is to provide the profit resp(i,j) * weight(i,j) to the total profit of date i:pi.

* Hence the term 4 in the final function is just the sum over the 500 dates of the daily profit pi. 

* If the evaluation function had only this term 4, then we could win the competition by being "lucky" : just find a trade that is massively profitable (or massively risky) and just trade this one. with some luck, we get a good score. 
That is not what Jane street wants.

* The function is called "utility score" because we want to obtain a "reasonable strategy". And to be reasonnable the returns should be positive and steady.

* That's why we have the term 3 in the evaluation function.
This term is basically a return (sum of all profits) divided by something like their variance.

* The Variance (or volatility) is similar to risk; if a strategy provides a 1% return on average (expectation) but does it with a 10% volatility, this is a very risky deal. the ratio 1%/10% is called a Sharpe ratio; it's the return weighted by risk. In that case it is the term 2.

* Then a sharpe ratio shouldn't be negative (useless), and cannot realistically be above 6 (otherwise returns would be 6 times their standard deviation which is unlikely), so the term 3 is just cutting off values below 0 or above 6.

* Finally this term is entering the final formula to penalize the profit made (term 4) by the risk taken (sharpe ratio).

And this explains the "utility function"


##### link for other basic questions on the competition 
https://www.kaggle.com/c/jane-street-market-prediction/discussion/198935

##### post on how to do a kaggle competition as a noob :-) 
https://www.kaggle.com/tanulsingh077/tackling-any-kaggle-competition-the-noob-s-way


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

##### Efficient market Hypothesis 

This hyopthesis states that prices reflect all the information available; P = E(Pt / It), and that there is by consequence no way to profit from some information to make a profit.
According to what "information"stands for there are 3 forms of EMH; strong, semi-string, weak:

* weak: past information (verified)

* semi-strong: past and public information (such as available in technical and fundamental analysis)

* Strong: all the information including insider, and anticipations, ...)

This relationship is true in the long-term, and this is the main argument to invest in trackers of market indices such as SP500, Nikkei225, HSI, etc ...

There is however a key point to keep in mind: this relationship is not instantaneous, and there is a mechanism that makes it possible.
Said otherwise it is possible to arbitrage and make a profit, so that in the end the EMH stands.

###### references:

* some links: http://www-stat.wharton.upenn.edu/~steele/Courses/434/434Context/EfficientMarket/IndexEMH.htm

* Machine learning and finance: Marcos lopez de prado http://www.quantresearch.org/Lectures.htm


