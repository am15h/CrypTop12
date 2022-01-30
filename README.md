# CrypTop12: A Dataset For Cryptocurrency Price Movement Prediction From Tweets And Historical Prices

This is the official repository for the release of the CrypTop12 dataset. If you would like to use our research, please cite the following:

A. Garg, T. Shah, V. K. Jain and R. Sharma, "[CrypTop12: A Dataset For Cryptocurrency Price Movement Prediction From Tweets And Historical Prices](https://ieeexplore.ieee.org/document/9680044)," 2021 20th IEEE International Conference on Machine Learning and Applications (ICMLA), 2021, pp. 379-384, doi: 10.1109/ICMLA52953.2021.00065.

Feel free to reach us out at [tanavshah@gmail.com](mailto:tanavshah@gmail.com) if you have any queries and suggestions for us!

## Overview

The dataset consists of two components: the historical prices and the tweets.


| Number of Coins | Duration | Number of Days | Average Tweets |
| ------------- | ------------- | ------------- | ------------- |
| 12 | 21/09/2017 to 27/03/2021 | 1255 | 38.28 |


## Components

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

* [Amish Garg](https://github.com/am15h)
* [Tanav Shah](https://github.com/TanavShah)
* [Vinay Kumar Jain](https://github.com/shacvin)
* Prof. Raksha Sharma
