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
  2. `source` field needs to be parsed and turned into `category` type variable
  3. `timestamp` and `retweeted_status_timestamp` columns should be `date_time` type variables
  4. `doggo / floofer / pupper / puppo` columns should be boolean variables for future use in regression models
  5. `lang` should be a `catgory` variable.
  6. `place` has only one record, so can be considered null.
  7. `contibutors`, `coordinates`, `favorited`, `geo`, `is_quote_status`, `possibly_sensitive`, `possibly_sensitive_appealable`, `retweeted`, `truncated` are all zero-content columns, so should be removed.
  8. `expanded_urls` column contains strings that need to be parsed and duplicates removed
      twitter_archive.expanded_urls = twitter_archive.expanded_urls.apply(lambda x: list(set(str(x).split(','))))


- Tidiness:
  1. `doggo / floofer / pupper / puppo` should be melted into a single category variable for better human use and visualisations
  2. Information about single observational units (tweets) is spread across three datatasets. They need to be merged into a single dataframe for ease of analysis.
  

---
# Brief
---
**Your goal**: wrangle WeRateDogs Twitter data to create interesting and trustworthy analyses and visualizations. The Twitter archive is great, but it only contains very basic tweet information. Additional gathering, then assessing and cleaning is required for "Wow!"-worthy analyses and visualizations.


1. The WeRateDogs Twitter archive. I am giving this file to you, so imagine it as a file on hand. Download this file manually by clicking the following link: twitter_archive_enhanced.csv

2. The tweet image predictions, i.e., what breed of dog (or other object, animal, etc.) is present in each tweet according to a neural network. This file (image_predictions.tsv) is hosted on Udacity's servers and should be downloaded programmatically using the Requests library and the following URL: https://d17h27t6h515a5.cloudfront.net/topher/2017/August/599fd2ad_image-predictions/image-predictions.tsv]

3. Each tweet's retweet count and favorite ("like") count at minimum, and any additional data you find interesting. Using the tweet IDs in the WeRateDogs Twitter archive, query the Twitter API for each tweet's JSON data using Python's Tweepy library and store each tweet's entire set of JSON data in a file called tweet_json.txt file. Each tweet's JSON data should be written to its own line. Then read this .txt file line by line into a pandas DataFrame with (at minimum) tweet ID, retweet count, and favorite count. Note: do not include your Twitter API keys, secrets, and tokens in your project submission.

Detect and document at least
* **Eight quality issues**
* **Two tidiness issues**
* **three insights** 
* **one visualization**

* Create a 300-600 word written report called wrangle_report.pdf or wrangle_report.html that briefly describes your wrangling efforts. This is to be framed as an internal document.

* Create a 250-word-minimum written report called act_report.pdf or act_report.html that communicates the insights and displays the visualization(s) produced from your wrangled data. This is to be framed as an external document, like a blog post or magazine article, for example.


