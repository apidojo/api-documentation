# Errors

All of our APIs uses the following error codes:

Error Code | Meaning
---------- | -------
400 | Bad Request -- Your request is invalid.
401 | Unauthorized -- Your API key is wrong.
403 | Forbidden -- Simply try to make the request again, our bot failed to overcome some bot detector.
404 | Not Found -- The specified query could not be found.
405 | Method Not Allowed -- You tried to access an endpoint with an invalid method.
406 | Not Acceptable -- You requested a format that isn't json.
410 | Gone -- The related cached data has been gone.
429 | Too Many Requests -- You're requesting too many queries at once! Slow down to 5 calls per second!
500 | Internal Server Error -- We had a problem with our server, please check your query and try again.
503 | Service Unavailable -- That the official server receive your request was too busy, and simply drop your request. Please try again.
