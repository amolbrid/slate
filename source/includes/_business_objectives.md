# Business Objectives


## Get all business objectives

```shell
curl 'https://toro.collective-media.net/api/business_objectives?advertiser_id=21' \
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
    "id": 82,
    "name": "Business Class - Web Prospect",
    "pixel_id": 10458,
    "pixel_name": "test.eg.1",
    "lookback": 30,
    "brand_id": 134,
    "created_at": "2014-08-21T16:49:39.166Z",
    "updated_at": "2014-08-21T16:49:39.166Z"
  },
  {
    "id": 85,
    "name": "Business Class BYOB Order",
    "pixel_id": 10521,
    "pixel_name": "test.eg.2",
    "lookback": 30,
    "brand_id": 134,
    "created_at": "2014-08-21T16:51:25.309Z",
    "updated_at": "2014-08-21T16:51:25.309Z"
  }
]
```

Get all business objectives for given advertiser or brand

### Request

`GET /api/business_objectives?advertiser_id={advertiser_id}&brand_id={brand_id}`

### Query parameters

Parameter | Description
--------- | -----------
advertiser_id | Filter business objectives by advertiser.
brand_id | Filter business objectBrand by brand.



## Create business objective

```shell
curl 'https://toro.collective-media.net/api/business_objectives' \
  -X POST \
  -H 'Accept: application/json' \
  -H 'Content-type: application/json' \
  -H 'Authorization: Token token="your_api_token"'
  -d '{"name":"Test business objective", "pixel_name":"abc.1", "brand_id":134, "lookback":30}'
```

> Response:

```http
HTTP/1.1 201 Created
Content-Type: application/json; charset=utf-8

{
  "id": 90,
  "name": "Test business objective",
  "pixel_id": 10465,
  "pixel_name": "abc.1",
  "lookback": 30,
  "brand_id": 134,
  "created_at": "2014-08-21T16:49:39.166Z",
  "updated_at": "2014-08-21T16:49:39.166Z"
}
```

Create business objective

### Request

`POST /api/business_objectives`

Field | Default | Description
--------- | ------- | -----------
name |  | **[Required]** Business objective name. This should be unique within brand.
lookback | | **[Required]** Lookback in days.
pixel_name | | **[Required]** Pixel name.
brand_id | | **[Required]** Brand id.


## Update business objective

```shell
curl 'https://toro.collective-media.net/api/business_objectives/90' \
  -X PUT \
  -H 'Accept: application/json' \
  -H 'Content-type: application/json' \
  -H 'Authorization: Token token="your_api_token"'
  -d '{"brand_id":134, "lookback":15}'
```

> Response:

```http
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

{
  "id": 90,
  "name": "Test business objective",
  "pixel_id": 10465,
  "pixel_name": "abc.1",
  "lookback": 15,
  "brand_id": 134,
  "created_at": "2014-08-21T16:49:39.166Z",
  "updated_at": "2014-08-21T16:49:39.166Z"
}
```

Updates business objective

`PUT /api/business_objectives/{business_objective_id}`

Field | Default | Description
--------- | ------- | -----------
brand_id | | **[Required]** Brand id.
name |  |  Business objective name. This should be unique within brand.
lookback | | Lookback in days.
pixel_name | | Pixel name.


## Fields Guide
Field | Description
--------- | -----------
id | Business objective id
name | Business objective name
pixel_id | Pixel id
pixel_name | Pixel name
lookback | Lookback in days
brand_id | Brand id.
