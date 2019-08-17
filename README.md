Wrangling this dataset has posed numerous challenges. Some of the most difficult challenges related to the open-ended nature of the wrangling process. Without a clear analysis brief it was rather difficult to prioritise and structure the wrangling process. Ultimately I had to make certain desicions / assumptions in order to move forward. These are:
* Analysis of this data will not engage with any questions related to the social context of this dataset. Therefore all retweets / replies and related fields were removed.
* Information contained in the `entities` and `extended_entities` is vast and expanding it all into separate columns is impractical.


Some interesting facts uncovered while wrangling this dataset:
* Twitter .json contains two different versions of 'favourite' spelling. The field 'favourites_count' inside 'user' field uses British spelling, while 'favorited' and 'favorite_count' in the main body of the json use American notation. Probably this was a deliberate design decision to avoid confusion around the different nature of these fields.

* The number of user's favourites stayed almost unchanged over the course of nearly 2 years (624 days to be precise)
* The user has posted on average 3.3 tweets per day.



## Possible analysis and visualisation questions
- is there a correlation between dog breed and the number of favorites and retweets?


### Twitter archive issues

- Quality:
  1.  `tweet_id`, `in_reply_to_user_id`,  `in_reply_to_status_id`, `retweeted_status_user_id` columns need to be strings
  2. source field needs to be parsed and turned into `category` type variable
  3. `timestamp` and `retweeted_status_timestamp` columns should be `date_time` type variables
  4. `doggo / floofer / pupper / puppo` columns should be boolean variables for future use in regression models

- Tidiness:
  1. `doggo / floofer / pupper / puppo` should be melted into a single category variable for better human use and visualisations
  2. Information about single observational units (tweets) is spread across three datatasets. They need to be merged into a single dataframe for ease of analysis.
