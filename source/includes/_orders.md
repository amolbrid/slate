# Orders

## Get all orders

```shell
curl 'https://toro.collective-media.net/api/orders?advertiser_id=2' \
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
    "id": 2,
    "name": "Disney Movie Club",
    "start_date": "2014-04-01",
    "end_date": "2014-04-30",
    "paused": false,
    "advertiser_id": 2,
    "created_at": "2014-03-27T17:35:59.553Z",
    "updated_at": "2015-01-06T20:26:45.579Z"
  },
  {
    "id": 11,
    "name": "Disney Q4 Domestic Conversion (DR/AB)",
    "start_date": "2014-07-02",
    "end_date": "2014-09-27",
    "paused": false,
    "advertiser_id": 2,
    "created_at": "2014-06-30T17:15:39.136Z",
    "updated_at": "2014-06-30T17:15:39.136Z"
  }
]
```

Get all orders for given advertiser

### Request

`GET /api/orders?advertiser_id={advertiser_id}`

### Query parameters

Parameter | Description
--------- | -----------
advertiser_id | **[Required]** Advertiser id.


## Get single order

```shell
curl 'https://toro.collective-media.net/api/orders/2' \
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
  "id": 2,
  "name": "Disney Movie Club",
  "start_date": "2014-04-01",
  "end_date": "2014-04-30",
  "advertiser_id": 2,
  "paused": false,
  "created_at": "2014-03-27T17:35:59.553Z",
  "updated_at": "2015-01-06T20:26:45.579Z"
}
```

Gets order by id.

### Request

`GET /api/orders/{order_id}`

## Create order

```shell
curl 'https://toro.collective-media.net/api/orders' \
  -X POST \
  -H 'Accept: application/json' \
  -H 'Content-type: application/json' \
  -H 'Authorization: Token token="your_api_token"' \
  -d '{"name": "Test Order", "advertiser_id": 2, "start_date":"2015-05-28", "end_date":"2015-06-15", "paused":false}'
```

> Response:

```http
HTTP/1.1 201 Created
Content-Type: application/json; charset=utf-8

{
  "id": 94,
  "name": "Test Order",
  "start_date": "2015-05-28",
  "end_date": "2015-06-15",
  "paused": false,
  "advertiser_id": 2,
  "created_at": "2015-05-26T20:13:35.675Z",
  "updated_at": "2015-05-26T20:13:35.675Z"
}
```

Creates order.

### Request

`POST /api/orders`

Field | Default | Description
--------- | ------- | -----------
name |  | **[Required]** Order name. This should be unique within advertiser.
advertiser_id | | **[Required]** Advertiser id.
start_date | | **[Required]** Order start date. Should be greater than today's date. Expected format: YYYY-MM-DD. e.g. 2015-05-28
end_date | | **[Required]** Order end date. Should be greater than 'start_date'. Expected format: YYYY-MM-DD. e.g. 2015-05-28
paused | | True to pause order.

## Update order

```shell
curl 'https://toro.collective-media.net/api/orders/94' \
  -X PUT \
  -H 'Accept: application/json' \
  -H 'Content-type: application/json' \
  -H 'Authorization: Token token="your_api_token"' \
  -d '{"name": "Update order"}'
```

> Response:

```http
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

{
  "id": 94,
  "name": "Update Order",
  "start_date": "2015-05-28",
  "end_date": "2015-06-15",
  "paused": false,
  "advertiser_id": 2,
  "created_at": "2015-05-26T20:13:35.675Z",
  "updated_at": "2015-05-26T20:14:35.675Z"
}
```

Updates order.

### Request

`PUT /api/orders/{order_id}`

Field | Default | Description
--------- | ------- | -----------
name |  | Order name. This should be unique within advertiser
start_date | | Order start date. Should be greater than today's date. Expected format: YYYY-MM-DD. e.g. 2015-05-28
end_date | | Order end date. Should be greater than 'start_date'. Expected format: YYYY-MM-DD. e.g. 2015-05-28
paused | | True to pause order.


## Fields Guide
Field | Description
--------- | -----------
id | Order id
name | Order name
start_date | Order start date
end_date | Order end date
advertiser_id | Advertiser to which order belongs
paused | True when order is paused. Otherwise false
