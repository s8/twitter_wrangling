### Downloaded archive issues

#### quality:
* remove all empty columns
- in_reply_to_status_id and in_reply_to_status_id_str >> should be strings
- in_reply_to_user_id and in_reply_to_user_id_str >> should be strings


#### tidiness:
* 'display_text_range' is an array that always starts with '0'
* 'source' column should be turned into a categorical variable
* unpack hashtags into a separate column and make it a categotical variable
* unpack tweet URLs into a separate column
* split 'created_at'column into separate date and time



#### tidiness:
- source field needs to be parsed and turned into category type variable
- 'display_text_range' is an array that always starts with '0'

#### quality:
- timestamp column should be a date_time type variable
- doggo / floofer / pupper / puppo columns should be boolean variables
- not matching id's from different sets?



### Twitter archive issues

- source field needs to be parsed and turned into `category` type variable
- `timestamp` column should be a `date_time` type variable
- `retweeted_status_timestamp` columnh should be a `date_time` variable
- `doggo / floofer / pupper / puppo` columns should be boolean variables

#### quality:
* remove all empty columns
- in_reply_to_status_id and in_reply_to_status_id_str >> should be strings
- in_reply_to_user_id and in_reply_to_user_id_str >> should be strings


#### tidiness:
* 'display_text_range' is an array that always starts with '0'
* 'source' column should be turned into a categorical variable
* unpack hashtags into a separate column and make it a categotical variable
* unpack tweet URLs into a separate column
* unpack `followers_count` from within `user` field
* unpack `friends_count` from within `user` field
* unpack `listed_coutn` from within `user` field
* unpack `statuses_count` from within `user` field
* split 'created_at'column into separate date and time
