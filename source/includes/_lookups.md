# Lookups

## Get DMAs

```shell
curl 'https://toro.collective-media.net/api/dmas' \
  -X GET \
  -H 'Accept: application/json' \
  -H 'Content-type: application/json' \
  -H 'Authorization: Token token="your_api_token"'
```

> Response:

```http
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

[
  {
    "code": 662,
    "name": "ABILENE-SWEETWATER"
  },
  {
    "code": 525,
    "name": "ALBANY, GA"
  },
  {
    "code": 532,
    "name": "ALBANY-SCHENECTADY-TROY"
  },
  {
    "code": 790,
    "name": "ALBUQUERQUE-SANTA FE"
  },
  {
    "code": 644,
    "name": "ALEXANDRIA, LA"
  },
  {
    "code": 583,
    "name": "ALPENA"
  }
]

```

Get DMAs sorted by name

### Request

`GET /api/dmas`

### Response

Field | Description
--------- | -----------
code | DMA code
name | DMA name

## Get States

```shell
curl 'https://toro.collective-media.net/api/states' \
  -X GET \
  -H 'Accept: application/json' \
  -H 'Content-type: application/json' \
  -H 'Authorization: Token token="your_api_token"'
```

> Response:

```http
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

[
  {
    "name": "Alabama",
    "abbreviation": "AK"
  },
  {
    "name": "Arizona",
    "abbreviation": "AZ"
  },
  {
    "name": "Arkansas",
    "abbreviation": "AR"
  },
  {
    "name": "California",
    "abbreviation": "CA"
  },
  {
    "name": "Colorado",
    "abbreviation": "CO"
  },
  {
    "name": "Connecticut",
    "abbreviation": "CT"
  },
  {
    "name": "Delaware",
    "abbreviation": "DE"
  }
]
```

Get all US states sorted by name

### Request

### Request

`GET /api/states`

### Response

Field | Description
--------- | -----------
name | State name
abbreviation | State abbreviation
