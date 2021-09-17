# CrypTop12: CryptoCurrency Dataset

A Dataset For Cryptocurrency Price Movement Prediction From Tweets And Historical Prices.

## Overview

The dataset consists of two components: the historical prices and the tweets.


| Number of Coins | Duration | Number of Days | Average Tweets |
| ------------- | ------------- | ------------- | ------------- |
| 12 | 21/09/2017 to 27/03/2021 | 1255 | 38.28 |


### Componenets

There are two main components:

#### Price

The price data is taken from [CoinMarketCap](https://coinmarketcap.com/).

The raw and preprocessed data for prices is organized as follows:

* ./price/raw
* ./price/preprocessed

#### Tweet

The tweet data is taken from [Twitter](https://twitter.com/).

The raw and preprocessed data for tweets is organized as follows:

* ./tweet/raw
* ./tweet/preprocessed