# Brands

## Get brands

```shell
curl 'https://toro.collective-media.net/api/brands?advertiser_id=20' \
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
    "id": 41,
    "name": "Consumer Cellular Gen. Business",
    "advertiser_id": 20,
    "created_at": "2014-03-28T13:00:52.943Z",
    "updated_at": "2014-03-28T13:00:52.943Z"
  },
  {
    "id": 19,
    "name": "Consumer DR Business",
    "advertiser_id": 20,
    "created_at": "2014-03-18T21:20:14.160Z",
    "updated_at": "2014-03-18T21:20:14.160Z"
  }
]
```

List of the brands for provided advertiser.

### Request

`GET /api/brands?advertiser_id={advertiser_id}`

### Query parameters

Parameter | Description
--------- | -----------
advertiser_id | **[Required]** Advertiser id.

### Response

Field | Description
--------- | -----------
id | Brand id
name | Brand name.
advertiser_id | Advertiser id.


## Get single brand

```shell
curl 'https://toro.collective-media.net/api/brands/19' \
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
  "id": 19,
  "name": "Consumer DR Business",
  "advertiser_id": 20,
  "created_at": "2014-03-18T21:20:14.160Z",
  "updated_at": "2014-03-18T21:20:14.160Z"
}
```

Gets brand by id

### Request

`GET /api/brands/{brand_id}`

### Response

Field | Description
--------- | -----------
id | Brand id.
name | Brand name.
advertiser_id | Advertiser id.


## Create brand


```shell
curl 'https://toro.collective-media.net/api/brands' \
  -X POST \
  -H 'Accept: application/json' \
  -H 'Content-type: application/json' \
  -H 'Authorization: Token token="your_api_token"' \
  -d '{"name": "Test Brand", "advertiser_id": 20}'
```

> Response:

```http
HTTP/1.1 201 Created
Content-Type: application/json; charset=utf-8

{
  "id": 41,
  "name": "Test Brand",
  "advertiser_id": 20,
  "created_at": "2014-03-18T21:20:14.160Z",
  "updated_at": "2014-03-18T21:20:14.160Z"
}
```

Creates brand.

### Request

`POST /api/brands`

Field | Default | Description
--------- | ------- | -----------
name |  | **[Required]** Brand name. This should be unique within advertiser.
advertiser_id | | **[Required]** Advertiser id

### Response

Field | Description
--------- | -----------
id | Brand id.
name | Brand name.
advertiser_id | Advertiser id.


## Update brand

```shell
curl 'https://toro.collective-media.net/api/brands/41' \
  -X POST \
  -H 'Accept: application/json' \
  -H 'Content-type: application/json' \
  -H 'Authorization: Token token="your_api_token"' \
  -d '{"name": "Update Brand"}'
```

> Response:

```http
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

{
  "id": 41,
  "name": "Update brand",
  "advertiser_id": 20,
  "created_at": "2014-03-18T21:20:14.160Z",
  "updated_at": "2014-03-18T21:20:14.160Z"
}
```

Updates brand.

### Request

`PUT /api/brands/{brand_id}`

Field | Default | Description
--------- | ------- | -----------
name |  | Brand name. This should be unique within advertiser

### Response

Field | Description
--------- | -----------
id | Brand id.
name | Brand name.
advertiser_id | Advertiser id.
