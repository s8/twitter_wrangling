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
