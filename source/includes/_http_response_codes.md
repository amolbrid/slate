## HTTP Response codes

### Successful Responses

Status Code | Description
---------- | -----------
200 | Ok -- Request succeeded
201 | Created -- Resource created successfully

### Error Responses

Status Code | Description
---------- | -------
400 | Bad Request -- Unable to understand or parse request
401 | Unauthorized -- Your API key is missing or invalid.
404 | Not Found -- The specified resource does not exist.
422 | Unprocessable Entity -- Request failed due to validation errors. Validate params and try again.
500 | Internal Server Error -- We had a problem with our server. Try again later.
