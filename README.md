# CrypTop12: CryptoCurrency Dataset

A Dataset For Cryptocurrency Price Movement Prediction From Tweets And Historical Prices.

## Overview

The dataset consists of two components: the historical prices and the tweets.


| Number of Coins | Duration | Number of Days | Average Tweets |
| ------------- | ------------- | ------------- | ------------- |
| 12 | 21/09/2017 to 27/03/2021 | 1255 | 38.28 |


## Componenets

There are two main components:

### Price

The price data is taken from [CoinMarketCap](https://coinmarketcap.com/).

The raw and preprocessed data for prices is organized as follows:

* ./price/raw
* ./price/preprocessed

### Tweet

The tweet data is taken from [Twitter](https://twitter.com/).

The raw and preprocessed data for tweets is organized as follows:

* ./tweet/raw
* ./tweet/preprocessed

## Data fields and format

### Prices

* Date: Date of observation (YYYY-MM-DD)
* High: Highest price on the given date
* Low: Lowest price on the given date
* Open: Opening price on the given date
* Close: Closing price on the given date
* Volume: Volume of transactions on the given date 
* Marketcap: Market capitalization in USD on the given date

**For pre-processed version:**

* We normalize *Open, Close, High, Low* as:

  * Normalized Price(t) = (Price(t) / Close Price(t - 1)) - 1

* We add an additional feature for movement percentage in the price dataset.

  * Movement%(t) = (Close Price(t) - Close Price(t - 1)) / Close Price(t - 1)

* We also remove the Marketcap attribute.

### Tweets

* id: Tweet Id
* username: Username of account posting the given tweet
* created_at: Date-Time of posting of the given tweet
* tweet: Content of tweet in raw format
* replies_count: Count of replies to the given tweet
* retweets_count: Count of retweets to the given tweet
* likes_count: Count of likes to the given tweet
* Follower_count: Count of followers of the username 

**For pre-processed version:**

* We use TweetTokenizer by NLTK for primary tokenization of each tweet.
* "AT_USER" prefix for the usernames mentioned in the tweet.
* "URL" for all the hyperlinks.
* "#" prefix for the hashtags.

## Authors

* Amish Garg (@am15h)
* Tanav Shah (@TanavShah)
* Vinay Kumar Jain (@shacvin)
* Prof. Raksha Sharma
