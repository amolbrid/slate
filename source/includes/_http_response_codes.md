# Response codes

Toro API uses conventional [HTTP response codes](http://en.wikipedia.org/wiki/List_of_HTTP_status_codes) to indicate success or failure of an API request. Below are details of success and error codes returned by Toro.

## Successful Responses

Status Code | Text | Description
---------- | ----------- | ---------
200 | Ok | Success!
201 | Created | Resource successfully created


## Error Responses

> In addition to HTTP status code, Toro API also returns error details for 400, 404 and 422 codes. Error response is in following format:

```json
{
  "message": "",
  "errors": [
    {
      "field": "",
      "messages": [
        "",
        ""
      ]
    }
  ]
}
```

> **errors** attribute in response is optional and is only populated when there are validation errors. Examples of error message:

```http
HTTP/1.1 404 Not Found
Content-Type: application/json; charset=utf-8

{
  "message":"Couldn't find Advertiser with 'id'=34567"
}
```

```
----
```

```http
HTTP/1.1 422 Unprocessable Entity
Content-Type: application/json; charset=utf-8

{
  "message": "Validation errors",
  "errors": [
    {
      "field": "name",
      "messages": [
        "Name can't be blank"
      ]
    }
  ]
}
```

```
----
```

```http
HTTP/1.1 400 Bad Request
Content-Type: application/json; charset=utf-8

{
  "message": "JSON parsing error: 795: unexpected token at '{\"name\":\"\"'"
}
```

Status Code | Text | Description
---------- | ------- | --------
400 | Bad Request | Unable to understand or parse request
401 | Unauthorized | Request is either missing API token or API token is invalid.
404 | Not Found | The specified resource does not exist.
422 | Unprocessable Entity | Request failed due to validation errors. Validate params and try again.
500 | Internal Server Error | We had a problem with our server. Try again later.
