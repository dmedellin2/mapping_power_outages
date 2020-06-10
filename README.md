![Image of Blackout](https://s7d2.scene7.com/is/image/TWCNews/blackoutlookbackjpg)

# Using Social Media to Map Power Outages Across the United States

### Contributors
[Matthew Malone](https://git.generalassemb.ly/mtm1186/)\
[Danielle Medellin](https://git.generalassemb.ly/dmedellin/)\
[Omar Smiley](https://git.generalassemb.ly/smileyo)

## Problem Statement

During a disaster, residential areas often experience massive power outages, that in many cases last for days. Traditional methods to map power outages include live feeds and data that is provided by major utility companies as well as on satellite data that capture the extent of light emitted at night. Real time updates on power outages can be extremely helpful to local residents, first responders and municipal governments. Social media platforms can be utiliized to obtain real time information on power outages and their causes. In combination with geo location data we can construct a tool to identify the locations of legitimate power outages. This tool will utilize posts on social media, specifically Twitter, to identify “hot spots” of concern and areas suffering from power outages. Following an event, the tool will scan relevant news or social media websites to identify areas likely to be suffering from power outage.

## Contents

In this repo, you will find the following notebooks in the `code` folder:

1. [Data Collection](./code/01_data_collection.ipynb)
2. [Data Cleaning & Word2Vec Model](./code/02_data_cleaning_and_word2vec.ipynb)
3. [EDA](./code/03_EDA.ipynb)
4. [Geovisual Mapping](./code/04_bokeh_mapping.ipynb)

All [data](./data/cleaned_tweets.csv) can be found in the `data` folder. Also included are [presentation slides](./power_outage_slides.pdf). 

## Python Package Requirements
In order to succesfully clone this repository, please insure to have the following packages installed into your Python environment:
* [Numpy](https://pypi.org/project/numpy/)
* [Pandas](https://pypi.org/project/pandas/)
* [Matplotlib](https://pypi.org/project/matplotlib/)
* [Seaborn](https://pypi.org/project/seaborn/)
* [Bokeh](https://pypi.org/project/bokeh/)
* [nltk](https://pypi.org/project/nltk/)
* [Tweetscraper](https://github.com/taspinar/twitterscraper)
* [Scikit Learn](https://pypi.org/project/scikit-learn/)

## Executive Summary
The rise of social media and ability for companies to leverage nontraditional data creates a prime opportunity to gain additional visibility into when, why and where electrical outages occur. Public citizens are valuable witnesses to outages and can provide real-time situational awareness in the form of social media posts to electrical companies, thereby helping shape responses. Connecting customers who want to provide meaningful content to utility providers in order to resolve outages faster is a mutually beneficial relationship that should be strengthened.

Our decision to use Twitter is based on its advantages regarding its audience and usage. While many social media platforms promote their “networks” and “friend circles”, Twitter’s primary audience has always been more global in nature. Twitter states on their guidelines that they offer Twitter in order “To give everyone the power to create and share ideas and information instantly without any barriers”.

Additionally, Twitter has emerged as the de-facto outlet for customer service for many companies. The ability to facilitate customer-to-business interactions in real time is an invaluable tool to companies looking to identify and resolve problems quickly. In fact, many organizations have deployed teams dedicated towards supporting customers through Twitter.

Twitter's focus on sharing ideas and information to the world served as our primary tool to identify outages. In order to scrape the largest number of tweets discussing power outages, we focused our efforts on five states: California, Texas, New York, Michigan and Ohio. These states led country in terms of power outages in 2017 according to Generac, the nation’s largest company in home backup generators. From each state we selected the three largest cities based on population. With a total of 15 cities, we ensured access to the largest possible Twitter user base to conduct our analysis. Due to the close proximity of the Michigan cities of Warren and Detroit, we decided to forgo Warren in favor of the next largest city, Ann Arbor.

Our data collection focused on querying Twitter for 34 search terms related to power outages. We limited our tweets to the past four years and the TwitterScraper package by default excluded any retweets. In total we collected 16,913 tweets between January 2016 and May 2020. Every tweet in the dataset originated from the geographic radii set for the respective city. This provided us with an additional level of assurance that the tweet was an actual account of that Twitter user’s experience. 


## Data Dictionary

| Parameter | Description | Data Type | Example |
| ------ | ------ | ------- | ------ |
| tweet_id | Numerical ID of the desired Tweet. | Integer | 123 |
| username | Twitter Username | String | "san jose now" |
| text | Text of the tweet | String | "power outage in cupertino bayarea" |
| tweet_date | Date and timestamp of tweet | String | 2016-01-01 04:20:00|
| search_term | Search term to query tweets | String | "#powerout" |
| city | City tweet originated from | String | "Dallas" |
| lat | Latitude of the coordinates used to search tweets | Integer | 37.3323 |
| long | Longitude of the coordinates used to search tweets | Integer | -121.853394 |
| radius | Search radius for tweets from the city's geographic coordinates  | String | "10mi" |
| name_and_tweet | Concatenated Twitter username and tweet text | String | "ttwn sf bay area power outage in cupertino bay..." |
| outage_sentiment | Sentiment value regarding power outages  | Integer | 0.5 |
| state | State tweet originated from | String | "Ohio" |


## Conclusions and Next Steps

Throughout this project we encountered many setbacks and made many compromises to our workflow and model, thus giving us various points for how to improve and enhance our work. Beginning with obtaining data from Twitter, as well as power outage data, we faced difficulties. Ideally, we would be able to use the actual Twitter API in order to gain more accurate location data for the tweets as well as do more comprehensive scrapes of Twitter data. We would also continue looking for, or purchasing, power outage history data as a way to add a confirmation of power outage to our model.

When we pulled in our tweets, we looked specifically at search terms that were related to power outages, which added bias to our model. In the future, we would pull as many tweets as possible, with no search terms, but within the same locations, to train our Word2Vec model with. Doing this would give us a better look at the inherent structure for how people talk about power outages, as opposed to other content.

The addition of the previously mentioned data could work to strengthen our tool of mapping power outages. Our goal is to have a real time interactive map that could display potential power outage areas based on tweets. Our tool would scrape Twitter in real time, analyze each tweet's outage sentiment, and display the location of where there are tweets with high outage sentiments. Additionally, the tool could collect this data and show historical information about previous power outages using the Slider function of Bokeh.

Our tool could be useful for both utility providers and customers needing real time information about power outages in their area. Having this tool constantly searching through Twitter could alert a utility company or first responders to an area in need. Customers could also check the tool to see if there is evidence of others experiencing outages in their area.


## References

- [Top 5 U.S. States For Power Outages, Generac (Feb, 2018)](https://www.generac.com/be-prepared/power-outages/top-5-states-where-power-outage-occur)
- [Twitter API Reference](https://developer.twitter.com/en/docs/tweets/search/api-reference)
- [Gensim Word2Vec Tutorial, Kavita Gensim](https://kavita-ganesan.com/gensim-word2vec-tutorial-starter-code/#.Xr3yDBNKhTa)
- [A Beginner’s Guide to Word2Vec and Neural Word Embeddings](https://pathmind.com/wiki/word2vec)
- [Lesson-NLP-i, Matt Brems](https://git.generalassemb.ly/DSI-US-11/5.03-lesson-nlp-i)
- [Lesson Word Vectors, Matt Brems](https://git.generalassemb.ly/DSI-US-11/8.07-lesson-word-vectors)
- [Can We Use Social Media to Locate Legitimate Power Outages?, Jen Hill,(April, 2017)](https://towardsdatascience.com/can-we-use-social-media-to-locate-legitimate-power-outages-7b7409708447)
- [Twitter Scraper, Adam Cohen](https://github.com/Adam395/Twitter-Scraper)
- [Elliptical (true) Mercator Projection](https://wiki.openstreetmap.org/wiki/Mercator#Elliptical_.28true.29_Mercator_Projection)
- [Twitter FAQ](https://investor.twitterinc.com/contact/faq/default.aspx)
- [Worst Job in America: Responding to Irate Tweets From New York City Subway Riders](https://www.wsj.com/articles/worst-job-in-america-responding-to-irate-tweets-from-new-york-city-subway-riders-1525790473)
