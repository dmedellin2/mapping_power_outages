![Image of Blackout](https://s7d2.scene7.com/is/image/TWCNews/blackoutlookbackjpg)

# Using Social Media to Map Power Outages Across the United States

[Mattew Malone](https://git.generalassemb.ly/dmedellin/)
[Danielle Medellin](https://git.generalassemb.ly/mtm1186/)
[Omar Smiley](https://git.generalassemb.ly/smileyo)

## Problem Statement
During a disaster, residential areas often experience massive power outages, that in many cases last for days. Traditional methods to map power outages include live feeds and data that is provided by major utility companies as well as on satellite data that capture the extent of light emitted at night. 
This tool will utilize posts on social media, specifically Twitter, to identify “hot spots” of concern and areas suffering from power outages. Following an event, the tool will scan relevant news or social media websites to identify areas likely to be suffering from power outage.


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
