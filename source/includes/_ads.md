# Ads

## Get all ads

```shell
curl 'https://toro.collective-media.net/api/ads?line_item_id=20' \
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
    "id": 34,
    "name": "Test Retargeting Ad",
    "ad_type_id": 2,
    "ad_type_name": "Retargeting",
    "pricing": "CPM",
    "paused": false,
    "paused_by_parent": false,
    "start_date": "2015-02-04",
    "end_date": "2015-06-30",
    "revenue_cpm": "1.0",
    "ordered_impressions": 1000,
    "include_unknown_zips": true,
    "include_unknown_dmas": false,
    "include_unknown_states": false,
    "business_objective_id": 15,
    "retargeting_pixel_id": 10895,
    "domain_list_id": null,
    "domain_list_included": true,
    "seller_member_ids": [

    ],
    "publisher_ids": [

    ],
    "accept_nil_publisher": null,
    "included_domains_string": "facebook.com\nyahoo.com",
    "excluded_domains_string": "",
    "targeted_zip_codes_string": "10001\n10002\n10003",
    "targeted_dmas": [
      525,
      532,
      790
    ],
    "targeted_states": [
      "AK",
      "AR",
      "AZ",
      "CA",
      "CO"
    ],
    "targeted_screens": [
      1,
      2,
      3,
      4
    ],
    "targeted_segments": null,
    "line_item_id": 20,
    "order_id": 10,
    "created_at": "2015-02-03T23:15:28.904Z",
    "updated_at": "2015-06-10T16:42:29.104Z"
  },
  {
    "id": 27,
    "name": "Test AO",
    "ad_type_id": 1,
    "ad_type_name": "Audience Optimization",
    "pricing": "CPM",
    "paused": false,
    "paused_by_parent": false,
    "start_date": "2014-11-06",
    "end_date": "2014-11-07",
    "revenue_cpm": "1.0",
    "ordered_impressions": 1000,
    "include_unknown_zips": false,
    "include_unknown_dmas": false,
    "include_unknown_states": false,
    "business_objective_id": 15,
    "retargeting_pixel_id": null,
    "domain_list_id": null,
    "domain_list_included": true,
    "seller_member_ids": [

    ],
    "publisher_ids": [

    ],
    "accept_nil_publisher": null,
    "included_domains_string": "",
    "excluded_domains_string": "",
    "targeted_zip_codes_string": "",
    "targeted_dmas": [
      525,
      532,
      662,
      790
    ],
    "targeted_states": [

    ],
    "targeted_screens": [

    ],
    "targeted_segments": "((55310 or 55311) or ((55312 or 57457) and 57456))",
    "line_item_id": 20,
    "order_id": 10,
    "created_at": "2014-11-05T16:36:12.234Z",
    "updated_at": "2015-05-08T13:42:40.582Z"
  }
]
```
Get all ads for given advertiser or order or line item sorted by ad name.

### Request

`GET /api/ads?advertiser_id={advertiser_id}&order_id={order_id}&line_item_id={line_item_id}`

### Query parameters

Parameter | Description
--------- | -----------
advertiser_id | Advertiser id.
order_id | Order id.
line_item_id | Line item id.

## Get single ad

```shell
curl 'https://toro.collective-media.net/api/ads/34?line_item_id=20' \
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
  "id": 34,
  "name": "Test Retargeting Ad",
  "ad_type_id": 2,
  "ad_type_name": "Retargeting",
  "pricing": "CPM",
  "paused": false,
  "paused_by_parent": false,
  "start_date": "2015-02-04",
  "end_date": "2015-06-30",
  "revenue_cpm": "1.0",
  "ordered_impressions": 1000,
  "include_unknown_zips": true,
  "include_unknown_dmas": false,
  "include_unknown_states": false,
  "business_objective_id": 15,
  "retargeting_pixel_id": 10895,
  "domain_list_id": null,
  "domain_list_included": true,
  "seller_member_ids": [

  ],
  "publisher_ids": [

  ],
  "accept_nil_publisher": null,
  "included_domains_string": "facebook.com\nyahoo.com",
  "excluded_domains_string": "",
  "targeted_zip_codes_string": "10001\n10002\n10003",
  "targeted_dmas": [
    525,
    532,
    790
  ],
  "targeted_states": [
    "AK",
    "AR",
    "AZ",
    "CA",
    "CO"
  ],
  "targeted_screens": [
    1,
    2,
    3,
    4
  ],
  "targeted_segments": null,
  "line_item_id": 20,
  "order_id": 10,
  "created_at": "2015-02-03T23:15:28.904Z",
  "updated_at": "2015-06-10T16:42:29.104Z"
}
```

Get ad for given id.

### Request

`GET /api/ads/{id}?line_item_id={line_item_id}`

### Query parameters

Parameter | Description
--------- | -----------
line_item_id | Line item id.

## Create ad

> Create 'create_ad' file with following json:

```json
{
  "name": "Api.Ad.1",
  "ad_type_id": 1,
  "start_date": "2015-01-06",
  "end_date": "2015-11-30",
  "pricing": "CPM",
  "ordered_impressions": 1000,
  "paused": false,
  "revenue_cpm": "1.0",
  "line_item_id": 20,
  "business_objective_id": 15,
  "domain_list_id": 3,
  "domain_list_included": true,
  "included_domains_string": "",
  "excluded_domains_string": "",
  "retargeting_pixel_id": null,

  "accept_nil_publisher": null,
  "publisher_ids": [

  ],
  "seller_member_ids": [

  ],
  "include_unknown_dmas": false,
  "include_unknown_states": false,
  "include_unknown_zips": false,
  "targeted_dmas": [
    525,
    532,
    662,
    790
  ],
  "targeted_states": [
    "AK",
    "AR",
    "AZ",
    "CA"
  ],
  "targeted_zip_codes_string": "10001\n10002\n10003",
  "targeted_screens": [
    1,
    2,
    3,
    4
  ],
  "targeted_segments": null
}

```

> Request:

```shell
curl 'https://toro.collective-media.net/api/ads/34?line_item_id=20' \
  -X POST \
  -H 'Accept: application/json' \
  -H 'Content-type: application/json' \
  -H 'Authorization: Token token="your_api_token"'
  -d @create_ad
```

> Response:

```http
HTTP/1.1 201 Created
Content-Type: application/json; charset=utf-8

{
  "id": 79,
  "name": "Api.Ad.1",
  "ad_type_id": 1,
  "ad_type_name": "Audience Optimization",
  "pricing": "CPM",
  "paused": false,
  "paused_by_parent": false,
  "start_date": "2015-01-06",
  "end_date": "2015-11-30",
  "revenue_cpm": "1.0",
  "ordered_impressions": 1000,
  "include_unknown_zips": false,
  "include_unknown_dmas": false,
  "include_unknown_states": false,
  "business_objective_id": 15,
  "retargeting_pixel_id": null,
  "domain_list_id": 3,
  "domain_list_included": true,
  "seller_member_ids": [

  ],
  "publisher_ids": [

  ],
  "accept_nil_publisher": null,
  "included_domains_string": "",
  "excluded_domains_string": "",
  "targeted_zip_codes_string": "10001\n10002\n10003",
  "targeted_dmas": [
    525,
    532,
    662,
    790
  ],
  "targeted_states": [
    "AK",
    "AR",
    "AZ",
    "CA"
  ],
  "targeted_screens": [
    1,
    2,
    3,
    4
  ],
  "targeted_segments": null,
  "line_item_id": 20,
  "order_id": 10,
  "created_at": "2015-06-11T14:31:38.551Z",
  "updated_at": "2015-06-11T14:31:38.642Z"
}

```

Creates ad

### Request

`POST /api/ads`

Field | Default | Description
--------- | ------- | -----------
name |  | **[Required]** Ad name.
line_item_id | | **[Required]** Line item id.
ad_type_id | | **[Required]** Ad type id. See **Ad Type** section below.
start_date | | **[Required]** Ad start date. Should be greater than today's date. Expected format: YYYY-MM-DD. e.g. 2015-05-28
end_date | | **[Required]** Ad end date. Should be greater than `start_date`. Expected format: YYYY-MM-DD. e.g. 2015-05-28
pricing | | **[Required]** Ad pricing. Valid values are CPM and CPA.
ordered_impressions | | Number of impressions desired. **Required** for CPM ad.
revenue_cpm | | Amount of revenue per 1000 impressions. Should not be more than 40. **Required** for CPM ad.
budget | | Amount to spend. **Required** for CPA ad. Should not be more than $1000 per day.
paused | | Set `true` to create paused ad.
business_objective_id | | Business object id. **Required** for _Click Optimized/RON/Viewability_ ad type.
domain_list_id | | Domain list id.
domain_list_included | | Set `true` when domain list is included.
included_domains_string | | Comma separated list of domains to include.
excluded_domains_string | | Comma separated list of domains to exclude.
retargeting_pixel_id | | Retargeting pixel id. **Required** for _Retargeting_ ad type.
accept_nil_publisher | |
publisher_ids | | Array of publisher ids.
seller_member_ids | | Array of seller member ids.
include_unknow_dmas | | Allow targeting on unknow dmas.
include_unknow_states | | Allow targeting on unknow states.
include_unknown_zips | | Allow targeting on unknow zips.
targeted_dmas | | Array of DMA codes.
targeted_states | | Array of state abbreviations.
targeted_zip_codes_string | | Comma or new line (\n) separated list of 5 digit zip codes.
targeted_screens | | Array of screen type ids. See **Screen Types** section below.
targeted_segments | | Targeted segments expression.
margin_goal | | Margin we'd like to make on these impressions, an integer between 0 and 100
add_strategy | | Auto create strategy.
add_creatives | | Create creatives for given ad size.
targeted_sizes | | Comma separated list of ad sizes.
assign_creatives | | Set `true` to assign creatives to strategy.


## Update ad

> Create 'update_ad' file with following json:

```json
{
  "id": 79,
  "start_date": "2015-07-06",
  "ordered_impressions": 10000,
  "targeted_zip_codes_string": "10001,10002,10003,10004,10005",
  "targeted_dmas": [
    525,
    532,
    662,
    790
  ],
  "targeted_states": [
    "AK",
    "AR",
    "AZ",
    "CA"
  ],
  "targeted_screens": [
    1,
    2,
    3,
    4
  ],
  "line_item_id": 20
}
```

> Request:

```shell
curl 'https://toro.collective-media.net/api/ads/79' \
  -X PUT \
  -H 'Accept: application/json' \
  -H 'Content-type: application/json' \
  -H 'Authorization: Token token="your_api_token"'
  -d @update_ad
```

> Response:

```http
HTTP/1.1 200 Ok
Content-Type: application/json; charset=utf-8

{
  "id": 79,
  "name": "Api.Ad.1",
  "ad_type_id": 1,
  "ad_type_name": "Audience Optimization",
  "pricing": "CPM",
  "paused": false,
  "paused_by_parent": false,
  "start_date": "2015-07-06",
  "end_date": "2015-11-30",
  "revenue_cpm": "1.0",
  "ordered_impressions": 10000,
  "include_unknown_zips": false,
  "include_unknown_dmas": false,
  "include_unknown_states": false,
  "business_objective_id": 15,
  "retargeting_pixel_id": null,
  "domain_list_id": 3,
  "domain_list_included": true,
  "seller_member_ids": [

  ],
  "publisher_ids": [

  ],
  "accept_nil_publisher": null,
  "included_domains_string": "",
  "excluded_domains_string": "",
  "targeted_zip_codes_string": "10001\n10002\n10003\n10004\n10005",
  "targeted_dmas": [
    525,
    532,
    662,
    790
  ],
  "targeted_states": [
    "AK",
    "AR",
    "AZ",
    "CA"
  ],
  "targeted_screens": [
    1,
    2,
    3,
    4
  ],
  "targeted_segments": null,
  "line_item_id": 20,
  "order_id": 10,
  "created_at": "2015-06-11T14:31:38.551Z",
  "updated_at": "2015-06-11T16:22:28.901Z"
}
```

Updates ad

### Request

`PUT /api/ads/{ad_id}`


Field | Default | Description
--------- | ------- | -----------
name |  | Ad name.
line_item_id | | **[Required]** Line item id.
ad_type_id | | Ad type id. Can be updated only if ad `start_date` is in future. See **Ad Type** section below.
start_date | | Ad start date. Should be greater than today's date. Expected format: YYYY-MM-DD. e.g. 2015-05-28
end_date | | Ad end date. Should be greater than `start_date`. Expected format: YYYY-MM-DD. e.g. 2015-05-28
pricing | | Ad pricing. Valid values are CPM and CPA.
ordered_impressions | | Number of impressions desired. **Required** for CPM ad.
revenue_cpm | | Amount of revenue per 1000 impressions. Should not be more than 40. **Required** for CPM ad.
budget | | Amount to spend. **Required** for CPA ad. Should not be more than $1000 per day.
paused | | Set `true` to create paused ad.
business_objective_id | | Business object id. **Required** for _Click Optimized/RON/Viewability_ ad type.
domain_list_id | | Domain list id.
domain_list_included | | Set `true` when domain list is included.
included_domains_string | | Comma separated list of domains to include.
excluded_domains_string | | Comma separated list of domains to exclude.
retargeting_pixel_id | | Retargeting pixel id. **Required** for _Retargeting_ ad type.
accept_nil_publisher | |
publisher_ids | | Array of publisher ids.
seller_member_ids | | Array of seller member ids.
include_unknow_dmas | | Allow targeting on unknown dmas.
include_unknow_states | | Allow targeting on unknown states.
include_unknown_zips | | Allow targeting on unknown zips.
targeted_dmas | | Array of DMA codes.
targeted_states | | Array of state abbreviations.
targeted_zip_codes_string | | Comma or new line (\n) separated list of 5 digit zip codes.
targeted_screens | | Array of screen type ids. See **Screen Types** section below.
targeted_segments | | Targeted segments expression.


## Fields Guide

Field |  Description
--------- | -----------
name | Ad name.
line_item_id | Line item id.
order_id | Order id.
ad_type_id | Ad type id. See **Ad Type** section below.
start_date | Ad start date. Format: YYYY-MM-DD. e.g. 2015-05-28
end_date | Ad end date. Format: YYYY-MM-DD. e.g. 2015-05-28
pricing | Ad pricing. Valid values are CPM and CPA.
ordered_impressions | Number of impressions desired. **Required** for CPM ad.
revenue_cpm | Amount of revenue per 1000 impressions. Should not be more than 40. **Required** for CPM ad.
budget | Amount to spend. **Required** for CPA ad. Should not be more than $1000 per day.
paused | `true` when ad is paused.
business_objective_id | Business object id. **Required** for _Click Optimized/RON/Viewability_ ad type.
domain_list_id | Domain list id.
domain_list_included | `true` when domain list is included.
included_domains_string | Comma separated list of domains to include.
excluded_domains_string | Comma separated list of domains to exclude.
retargeting_pixel_id | Retargeting pixel id for _Retargeting_ ad type.
accept_nil_publisher |
publisher_ids | Array of publisher ids.
seller_member_ids | Array of seller member ids.
include_unknow_dmas | Allow targeting on unknown dmas.
include_unknow_states | Allow targeting on unknown states.
include_unknown_zips | Allow targeting on unknown zips.
targeted_dmas | Array of DMA codes.
targeted_states | Array of state abbreviations.
targeted_zip_codes_string | Comma or new line (\n) separated list of 5 digit zip codes.
targeted_screens | Array of screen type ids. See **Screen Types** section below.
targeted_segments | Targeted segments expression.

### Ad Types

Id | Name
----- | -----
1 | Audience Optimization
2 | Retargeting
3 | RON
4 | Click Optimized
5 | Viewability

### Screen Types

Id | Name
----- | -----
1 | Personal Computer
2 | Phone (Mobile Web)
3 | Tablet
4 | Other / Unknown
