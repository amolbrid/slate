# Domain Lists

## Get all domain lists

```shell
curl 'https://toro.collective-media.net/api/domain_lists?advertiser_id=20' \
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
    "id": 6,
    "name": "Sample Advertiser Whitelist",
    "domains_string": "msn.com,yahoo.com",
    "advertiser_id": 20,
    "created_at": "2015-04-15T13:35:18.990Z",
    "updated_at": "2015-04-15T13:35:18.998Z"
  },
  {
    "id": 4,
    "name": "Just List 2",
    "domains_string": "cbs.com,reditt.com",
    "advertiser_id": 20,
    "created_at": "2015-03-19T18:55:41.707Z",
    "updated_at": "2015-03-19T18:55:41.714Z"
  }
]
```

List of domain lists for given advertiser.

### Request

`GET /api/domain_lists?advertiser_id={advertiser_id}`

### Query parameters

Parameter | Description
--------- | -----------
advertiser_id | **[Required]** Advertiser id.

### Response

Field | Description
--------- | -----------
id | Domain list id
name | Domain list name.
advertiser_id | Advertiser id.
domains_string | Comma separated list of domain names.


## Get single domain list

```shell
curl 'https://toro.collective-media.net/api/domain_lists/6?advertiser_id=20' \
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
  "id": 6,
  "name": "Sample Advertiser Whitelist",
  "domains_string": "msn.com,yahoo.com",
  "advertiser_id": 20,
  "created_at": "2015-04-15T13:35:18.990Z",
  "updated_at": "2015-04-15T13:35:18.998Z"
}
```

Get domain list by id.

### Request

`GET /api/domain_lists/{domain_list_id}?advertiser_id={advertiser_id}`

### Query parameters

Parameter | Description
--------- | -----------
advertiser_id | **[Required]** Advertiser id.
domain_list_id | **[Required]** Domain list id.

### Response

Field | Description
--------- | -----------
id | Domain list id
name | Domain list name.
advertiser_id | Advertiser id.
domains_string | Comma separated list of domain names.

## Create domain list

```shell
curl 'https://toro.collective-media.net/api/domain_lists' \
  -X POST \
  -H 'Accept: application/json' \
  -H 'Content-type: application/json' \
  -H 'Authorization: Token token="your_api_token"'
  -d '{"name": "Test Domain list", "advertiser_id": 20, "domains_string": "nytimes.com, cnn.com"}'
```

> Response:

```http
HTTP/1.1 201 Created
Content-Type: application/json; charset=utf-8

{
  "id": 10,
  "name": "Test Domain list",
  "domains_string": "nytimes.com, cnn.com",
  "advertiser_id": 20,
  "created_at": "2015-04-15T13:35:18.990Z",
  "updated_at": "2015-04-15T13:35:18.998Z"
}
```

Creates domain list

`POST /api/domain_lists`

Field | Default | Description
--------- | ------- | -----------
name |  | **[Required]** Domain list name. This should be unique within advertiser
advertiser_id | | **[Required]** Advertiser id.
domains_string | | Comma separated domain list.

### Response

Field | Description
--------- | -----------
id | Domain list id
name | Domain list name.
advertiser_id | Advertiser id.
domains_string | Comma separated list of domain names.


## Update domain list

```shell
curl 'https://toro.collective-media.net/api/domain_lists/10' \
  -X PUT \
  -H 'Accept: application/json' \
  -H 'Content-type: application/json' \
  -H 'Authorization: Token token="your_api_token"'
  -d '{"advertiser_id": 20, "domains_string": "nytimes.com, cnn.com, cbs.com"}'
```

> Response:

```http
HTTP/1.1 200 Ok
Content-Type: application/json; charset=utf-8

{
  "id": 10,
  "name": "Test Domain list",
  "domains_string": "nytimes.com, cnn.com, cbs.com",
  "advertiser_id": 20,
  "created_at": "2015-04-15T13:35:18.990Z",
  "updated_at": "2015-04-15T13:40:18.998Z"
}
```
Updates brand.

### Request

`PUT /api/domain_lists/{domain_list_id}`

Field | Default | Description
--------- | ------- | -----------
name |  | Domain list name. This should be unique within advertiser
advertiser_id | | **[Required]** Advertiser id.
domains_string | | Comma separated domain list.

### Response

Field | Description
--------- | -----------
id | Domain list id
name | Domain list name.
advertiser_id | Advertiser id.
domains_string | Comma separated list of domain names.
