Wrangling this dataset has posed numerous challenges. Some of the most difficult challenges related to the open-ended nature of the wrangling process. Without a clear analysis brief it was rather difficult to prioritise and structure the wrangling process. Ultimately I had to make certain desicions / assumptions in order to move forward. These are:
* Analysis of this data will not engage with any questions related to the social context of this dataset. Therefore all retweets / replies and related fields were removed.
* Information contained in the `entities` and `extended_entities` is vast and expanding it all into separate columns is impractical.


Twitter .json contains two different versions of 'favourite' spelling. The field 'favourites_count' inside 'user' field uses British spelling, while 'favorited' and 'favorite_count' in the main body of the json use American notation.
