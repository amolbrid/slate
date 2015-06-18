# LineItems

## Get line items

```shell
curl 'https://toro.collective-media.net/api/line_items?order_id=9' \
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
    "id": 12,
    "name": "Test Line Item - 1",
    "paused": false,
    "paused_by_parent": false,
    "brand_id": 107,
    "order_id": 9,
    "created_at": "2014-06-30T12:34:29.117Z",
    "updated_at": "2014-06-30T12:49:02.872Z"
  },
  {
    "id": 158,
    "name": "Test Line Item - 2",
    "paused": false,
    "paused_by_parent": false,
    "brand_id": 107,
    "order_id": 9,
    "created_at": "2015-01-12T22:02:42.039Z",
    "updated_at": "2015-01-12T22:02:42.039Z"
  }
]
```

Gets line items for given order.

### Request

`GET /api/line_items?order_id={order_id}`

### Query parameters

Parameter | Description
--------- | -----------
order_id | **[Required]** Order id.


## Get single line item

```shell
curl 'https://toro.collective-media.net/api/line_items/12' \
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
  "id": 12,
  "name": "Test Line Item - 1",
  "paused": false,
  "paused_by_parent": false,
  "brand_id": 107,
  "order_id": 9,
  "created_at": "2014-06-30T12:34:29.117Z",
  "updated_at": "2014-06-30T12:49:02.872Z"
}
```

Gets line item by give id

### Request

`GET /api/line_items/{line_item_id}`

## Create line item

```shell
curl 'https://toro.collective-media.net/api/line_items' \
  -X POST \
  -H 'Accept: application/json' \
  -H 'Content-type: application/json' \
  -H 'Authorization: Token token="your_api_token"' \
  -d '{"name": "Test Line Item", "order_id": 9, "paused": false, "brand_id": 107}'
```

> Response:

```http
HTTP/1.1 201 Created
Content-Type: application/json; charset=utf-8

{
  "id": 12,
  "name": "Test Line Item",
  "paused": false,
  "paused_by_parent": false,
  "brand_id": 107,
  "order_id": 9,
  "created_at": "2014-06-30T12:34:29.117Z",
  "updated_at": "2014-06-30T12:49:02.872Z"
}
```

Creates line item.

### Request

`POST /api/line_items`

Field | Default | Description
--------- | ------- | -----------
name |  | **[Required]** Line item name. This should be unique for order.
order_id | | **[Required]** Order id.
paused | | True to pause order.
brand_id | | **[Required]** Brand id.

## Update line item

```shell
curl 'https://toro.collective-media.net/api/line_items/12' \
  -X PUT \
  -H 'Accept: application/json' \
  -H 'Content-type: application/json' \
  -H 'Authorization: Token token="your_api_token"' \
  -d '{"id": 12, "name": "Update Test Line Item", order_id": 9, "paused": false, "brand_id": 107}'
```

> Response:

```http
HTTP/1.1 200 Ok
Content-Type: application/json; charset=utf-8

{
  "id": 12,
  "name": "Update Test Line Item",
  "paused": false,
  "paused_by_parent": false,
  "brand_id": 107,
  "order_id": 9,
  "created_at": "2014-06-30T12:34:29.117Z",
  "updated_at": "2014-06-30T12:49:02.872Z"
}
```

Updates line item.

Field | Default | Description
--------- | ------- | -----------
name |  | Line item name. This should be unique for order.
order_id | | **[Required]** Order id.
paused | | True to pause order.
brand_id | | Brand id.


## Fields Guide
Field | Description
--------- | -----------
id | Line item id
name | Line item name
order_id | Order to which line item belongs
brand_id | Brand id
paused | True when line item is paused. Otherwise false
paused_by_parent | True when line item is paused because order is paused.
