![Image of Blackout](https://s7d2.scene7.com/is/image/TWCNews/blackoutlookbackjpg)

# Using Social Media to Map Power Outages Across the United States

### Contributors
[Matthew Malone](https://git.generalassemb.ly/mtm1186/)\
[Danielle Medellin](https://git.generalassemb.ly/dmedellin/)\
[Omar Smiley](https://git.generalassemb.ly/smileyo)

## Problem Statement

During a disaster, residential areas often experience massive power outages, that in many cases last for days. Traditional methods to map power outages include live feeds and data that is provided by major utility companies as well as on satellite data that capture the extent of light emitted at night. 
This tool will utilize posts on social media, specifically Twitter, to identify “hot spots” of concern and areas suffering from power outages. Following an event, the tool will scan relevant news or social media websites to identify areas likely to be suffering from power outage.


## Executive Summary
The rise of social media and ability for companies to leverage nontraditional data creates a prime opportunity to gain additional visibility into when, why and where electrical outages occur. Public citizens are valuable witnesses to outages and can provide real-time situational awareness in the form of social media posts to electrical companies, thereby helping shape responses. Connecting customers who want to provide meaningful content to utility providers in order to resolve outages faster is a mutually beneficial relationship that should be strenthened.

Twitter's focus on sharing ideas and information to the world served as our primary tool to identify outages. In order to scrape the largest number of tweets discussing power outages, we focused our efforts on five states: California, Texas, New York, Michigan and Ohio. These states led country in terms of power outages in 2017 according to Generac, the nation’s largest company in home backup generators. From each state we selected the three largest cities based on population. With a total of 15 cities, we ensured access to the largest possible Twitter user base to conduct our analysis.


## Data Dictionary

| Parameter | Description | Data Type | Example |
| ------ | ------ | ------- | ------ |
| tweet_id | Numerical ID of the desired Tweet. | Integer | 123 |
| username | Twitter Username | String | "san jose now" |
| text | Text of the tweet | String | "power outage in cupertino bayarea" |
| tweet_date | Date of tweet | String | 2016-01-01 |
| search_term | Search term to query tweets | String | "#powerout" |
| city | City tweet originated from | String | "Dallas" |
| lat | Latitude of the coordinates used to search tweets | integer | 37.3323 |
| long | Longitude of the coordinates used to search tweets | integer | -121.853394 |
| radius | Search radius for tweets from the city's geographic coordinates  | String | "10mi" |
| name_and_tweet | Concatenated Twitter username and tweet text | String | "ttwn sf bay area power outage in cupertino bay..." |
| outage_sentiment | Sentiment value regarding power outages  | Integer | 0.5 |
| state | State tweet originated from | String | "Ohio" |


## References
https://help.twitter.com/en/rules-and-policies/twitter-services-and-corporate-affiliates \
https://www.wsj.com/articles/worst-job-in-america-responding-to-irate-tweets-from-new-york-city-subway-riders-1525790473 \
https://www.generac.com/be-prepared/power-outages/top-5-states-where-power-outage-occur \
https://developer.twitter.com/en/docs/tweets/search/api-reference

