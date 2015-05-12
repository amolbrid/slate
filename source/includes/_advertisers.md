# Advertisers

## Get all advertisers

```ruby
# ruby code here
```

```scala
// scala code here
```

```shell
curl 'https://toro.collective-media.net/api/advertisers' \
  -X GET \
  -H 'Accept: application/json' \
  -H 'Content-type: application/json' \
  -H 'Authorization: Token token="your_api_token"'
```

> Response

```json
[
  {
    "id": 1,
    "name": "Christoph",
    "testmode": true,
    "inventory_tier_id": 1,
    "created_at": "2013-04-22T12:51:32.464Z",
    "updated_at": "2013-04-22T12:51:32.464Z"
  },
  {
    "id": 3,
    "name": "Yahoo!",
    "testmode": false,
    "inventory_tier_id": 1,
    "created_at": "2013-07-22T17:32:34.164Z",
    "updated_at": "2013-07-22T17:32:34.164Z"
  },
  {
    "id": 4,
    "name": "Teleflora",
    "testmode": false,
    "inventory_tier_id": 1,
    "created_at": "2013-07-23T14:46:03.243Z",
    "updated_at": "2013-07-23T14:46:03.243Z"
  }
]
```

List of the all advertisers.

### Request

`GET https://toro.collective-media.net/api/advertisers`

### Response

Field | Default | Description
--------- | ------- | -----------
name |  | Name of the advertiser.
testmode | false | If set to false, advertiser will be only for testing purpose. This attribute can only be set by 'admin' user.
inventory_tier_id | | Id of inventory package

## Get single advertiser

```ruby
# ruby code here
```

```scala
// scala code here
```

```shell
curl 'https://toro.collective-media.net/api/advertisers/31' \
  -X GET \
  -H 'Accept: application/json' \
  -H 'Content-type: application/json' \
  -H 'Authorization: Token token="your_api_token"'
```

> The above request returns:

```json
{
  "id": 3,
  "name": "Yahoo!",
  "testmode": false,
  "inventory_tier_id": 1,
  "created_at": "2013-07-22T17:32:34.164Z",
  "updated_at": "2013-07-22T17:32:34.164Z"
}
```

Gets advertiser by id

### Request

`GET https://toro.collective-media.net/api/advertisers/{advertiser_id}`

### Response

Field | Description
--------- | -----------
name | Name of the advertiser.
testmode | If set to false, advertiser will be only for testing purpose. This attribute can only be set by 'admin' user.
inventory_tier_id | Id of inventory package


## Create advertiser

```ruby
# ruby code here
```

```scala
// scala code here
```

```shell
curl 'https://toro.collective-media.net/api/advertisers' \
  -X POST \
  -H 'Accept: application/json' \
  -H 'Content-type: application/json' \
  -H 'Authorization: Token token="your_api_token"' \
  -d '{"name": "Test Advertiser"}'
```

> Response:

```json
{
  "id":148,
  "name":"Test Advertiser",
  "testmode":false,
  "inventory_tier_id":1,
  "created_at":"2015-05-05T18:44:06.183Z",
  "updated_at":"2015-05-05T18:44:06.183Z",
}
```

Creates advertiser.

### Request

`POST https://toro.collective-media.net/api/advertisers`

Field | Default | Description
--------- | ------- | -----------
name |  | **[Required]** Name of the advertiser.
testmode | false | If set to false, advertiser will be only for testing purpose. This attribute can only be set by 'admin' user.

### Response

Field | Description
--------- | -----------
name | Name of the advertiser.
testmode | If set to false, advertiser will be only for testing purpose. This attribute can only be set by 'admin' user.
inventory_tier_id | Id of inventory package

## Update advertiser

```ruby
# ruby code here
```

```scala
// scala code here
```

```shell
curl 'https://toro.collective-media.net/rtb_advertisers/32' \
  -X PUT \
  -H 'Accept: application/json' \
  -H 'Content-type: application/json' \
  -H 'Authorization: Token token="your_api_token"' \
  -d '{name": "Test Advertiser"}'
```

> Updates advertiser name and returns 204 HTTP status code

Updates advertiser.

### Request

`PUT https://toro.collective-media.net/api/advertisers/{:advertiser_id}`

Field | Default | Description
--------- | ------- | -----------
name |  | **[Required]** Name of the advertiser.

### Response

Returns empty response with 204 HTTP Status code.
