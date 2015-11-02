# Inventory Tier

## Get all inventory tiers

```shell
curl 'https://toro.collective-media.net/api/inventory_tiers' \
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
    "id": 3,
    "name": "Click Performance (Gold Inventory)",
    "seller_member_ids": [

    ],
    "publisher_ids": [

    ],
    "is_default": false,
    "included_domains_string": "1234.com",
    "excluded_domains_string": "",
    "ad_type_ids": [
      4
    ],
    "created_at": "2015-04-14T18:16:03.656Z",
    "updated_at": "2015-05-01T18:02:54.448Z"
  },
  {
    "id": 2,
    "name": "Super Premium",
    "seller_member_ids": [
      1,
      2,
      3,
      5
    ],
    "publisher_ids": [
      1,
      2
    ],
    "is_default": false,
    "included_domains_string": "",
    "excluded_domains_string": "",
    "ad_type_ids": [

    ],
    "created_at": "2014-07-08T20:38:02.443Z",
    "updated_at": "2014-07-08T20:38:11.988Z"
  },
  {
    "id": 4,
    "name": "Viewability Performance (Gold Inventory)",
    "seller_member_ids": [

    ],
    "publisher_ids": [

    ],
    "is_default": false,
    "included_domains_string": "",
    "excluded_domains_string": "",
    "ad_type_ids": [
      5
    ],
    "created_at": "2015-04-20T15:07:53.784Z",
    "updated_at": "2015-04-28T17:34:48.632Z"
  },
  {
    "id": 1,
    "name": "Whitelist",
    "seller_member_ids": [
      1
    ],
    "publisher_ids": [

    ],
    "is_default": false,
    "included_domains_string": "",
    "excluded_domains_string": "",
    "ad_type_ids": [
      1,
      2,
      3,
      4
    ],
    "created_at": "2014-07-03T14:46:23.232Z",
    "updated_at": "2015-04-28T20:07:35.236Z"
  }
]
```

Get all inventory tiers available in system.

### Request

`GET /api/inventory_tiers`


## Get inventory tier

```shell
curl 'https://toro.collective-media.net/api/inventory_tiers/1' \
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
  "id": 1,
  "name": "Whitelist",
  "seller_member_ids": [
    1
  ],
  "publisher_ids": [

  ],
  "is_default": false,
  "included_domains_string": "",
  "excluded_domains_string": "",
  "ad_type_ids": [
    1,
    2,
    3,
    4
  ],
  "created_at": "2014-07-03T14:46:23.232Z",
  "updated_at": "2015-04-28T20:07:35.236Z"
}
```

Get inventory_tier for given id.

### Request

`GET /api/inventory_tiers/{inventory_tier_id}`


## Create inventory tier

```shell
curl 'https://toro.collective-media.net/api/inventory_tiers' \
  -X POST \
  -H 'Accept: application/json' \
  -H 'Content-type: application/json' \
  -H 'Authorization: Token token="your_api_token"' \
  -d '{"name": "Test Inventory tier", "ad_type_ids": [2,3], "seller_member_ids": [1,2,3]}'
```

> Response:

```http
HTTP/1.1 201 Created
Content-Type: application/json; charset=utf-8

{
  "id": 2,
  "name": "Test Inventory tier",
  "seller_member_ids": [
    1,
    2,
    3
  ],
  "publisher_ids": [

  ],
  "is_default": false,
  "included_domains_string": "",
  "excluded_domains_string": "",
  "ad_type_ids": [
    2,
    3
  ],
  "created_at": "2014-07-03T14:46:23.232Z",
  "updated_at": "2015-04-28T20:07:35.236Z"
}
```

Creates inventory tier.

### Request

`POST /api/inventory_tiers`

Field | Description
--------- | ------- | -----------
name |  **[Required]** Inventory tier name. This should be unique.
seller_member_ids | Seller member ids
publisher_ids | Publisher ids
included_domains_string | Comma separated list of domains to include
excluded_domains_string | Comma separated list of domains to exclude
ad_type_ids | Ad type ids

## Update inventory tier

```shell
curl 'https://toro.collective-media.net/api/inventory_tiers/2' \
  -X PUT \
  -H 'Accept: application/json' \
  -H 'Content-type: application/json' \
  -H 'Authorization: Token token="your_api_token"' \
  -d '{"included_domains_string"="google.com, facebook.com, collective.com"}'
```

> Response:

```http
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

{
  "id": 2,
  "name": "Test Inventory tier",
  "seller_member_ids": [
    1,
    2,
    3
  ],
  "publisher_ids": [

  ],
  "is_default": false,
  "included_domains_string": "google.com, facebook.com, collective.com",
  "excluded_domains_string": "",
  "ad_type_ids": [
    2,
    3
  ],
  "created_at": "2014-07-03T14:46:23.232Z",
  "updated_at": "2015-04-28T20:07:35.236Z"
}
```

Updates order.

### Request

`PUT /api/inventory_tiers/{inventory_tier_id}`

Field | Description
--------- | ------- | -----------
name | **[Required]** Inventory tier name. This should be unique.
seller_member_ids | Seller member ids
publisher_ids | Publisher ids
included_domains_string | Comma separated list of domains to include
excluded_domains_string | Comma separated list of domains to exclude
ad_type_ids | Ad type ids


## Fields Guide

Field | Type |  Description
--------- | ----------- | --------
id | Number | Inventory tier id
name | String | Inventory tier name.
seller_member_ids | Array | Seller member ids
publisher_ids | Array | Publisher ids
included_domains_string | String | Comma separated list of domains to include
excluded_domains_string | String | Comma separated list of domains to exclude
ad_type_ids | Array | Ad type ids
created_at | DateTime | Date and time when inventory tier was created
updated_at | DateTime | Date and time when inventory tier was last updated
