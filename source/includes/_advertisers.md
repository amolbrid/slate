# Advertisers

## Get all advertisers

```shell
curl 'https://toro.collective-media.net/api/advertisers' \
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
    "id": 1,
    "name": "Christoph",
    "testmode": true,
    "created_at": "2013-04-22T12:51:32.464Z",
    "updated_at": "2013-04-22T12:51:32.464Z"
  },
  {
    "id": 3,
    "name": "Yahoo!",
    "testmode": false,
    "created_at": "2013-07-22T17:32:34.164Z",
    "updated_at": "2013-07-22T17:32:34.164Z"
  },
  {
    "id": 4,
    "name": "Teleflora",
    "testmode": false,
    "created_at": "2013-07-23T14:46:03.243Z",
    "updated_at": "2013-07-23T14:46:03.243Z"
  }
]
```

List of the all advertisers.

### Request

`GET /api/advertisers`

### Response

Field | Description
--------- | -----------
id | Advertiser id
name | Name of the advertiser.
testmode | True when advertiser is used for testing purpose. Otherwise false.


## Get single advertiser

```shell
curl 'https://toro.collective-media.net/api/advertisers/31' \
  -X GET \
  -H 'Accept: application/json' \
  -H 'Content-type: application/json' \
  -H 'Authorization: Token token="your_api_token"'
```

> Response:

```http
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

{
  "id": 3,
  "name": "Yahoo!",
  "testmode": false,
  "created_at": "2013-07-22T17:32:34.164Z",
  "updated_at": "2013-07-22T17:32:34.164Z"
}
```

Gets advertiser by id

### Request

`GET /api/advertisers/{advertiser_id}`

### Response

Field | Description
--------- | -----------
id | Advertiser id
name | Name of the advertiser.
testmode | True when advertiser is used for testing purpose. Otherwise false.


## Create advertiser

```shell
curl 'https://toro.collective-media.net/api/advertisers' \
  -X POST \
  -H 'Accept: application/json' \
  -H 'Content-type: application/json' \
  -H 'Authorization: Token token="your_api_token"' \
  -d '{"name": "Test Advertiser"}'
```

> Response:

```http
HTTP/1.1 201 Created
Content-Type: application/json; charset=utf-8

{
  "id":148,
  "name":"Test Advertiser",
  "testmode":false,
  "created_at":"2015-05-05T18:44:06.183Z",
  "updated_at":"2015-05-05T18:44:06.183Z"
}
```

Creates advertiser.

### Request

`POST /api/advertisers`

Field | Default | Description
--------- | ------- | -----------
name |  | **[Required]** Name of the advertiser.
testmode | false | When set to true, advertiser will be only for testing purpose. This attribute can only be set by 'admin' user.

### Response

Field | Description
--------- | -----------
id | Advertiser id
name | Name of the advertiser.
testmode | True when advertiser is used for testing purpose. Otherwise false.


## Update advertiser

```shell
curl 'https://toro.collective-media.net/rtb_advertisers/32' \
  -X PUT \
  -H 'Accept: application/json' \
  -H 'Content-type: application/json' \
  -H 'Authorization: Token token="your_api_token"' \
  -d '{name": "Test Advertiser"}'
```

> Response:

```http
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

{
  "id":148,
  "name":"Test Advertiser",
  "testmode":false,
  "created_at":"2015-05-05T18:44:06.183Z",
  "updated_at":"2015-05-05T18:44:06.183Z"
}
```

### Request

`PUT /api/advertisers/{:advertiser_id}`

Field | Default | Description
--------- | ------- | -----------
name |  | Name of the advertiser.
testmode | false | When set to true, advertiser will be only for testing purpose. This attribute can only be set by 'admin' user.

### Response

Field | Description
--------- | -----------
id | Advertiser id
name | Name of the advertiser.
testmode | True when advertiser is used for testing purpose. Otherwise false.
