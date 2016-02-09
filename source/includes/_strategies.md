# Strategies

## Get all strategies

```shell
curl 'https://toro.collective-media.net/api/strategies?ad_id=2' \
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
    "name": "Standard",
    "amp_kv": "standard",
    "margin_goal": 11,
    "user_partition": "100.0",
    "budget_partition": "100.0",
    "ramp_end": "0",
    "end_step": "Hours",
    "ramp_begin": "0.5",
    "begin_step": "Hours",
    "min_bid": "0.01",
    "max_cost": "50.0",
    "paused": false,
    "paused_by_parent": false,
    "control_group": false,
    "ad_id": 2,
    "created_at": "2014-07-02T21:00:23.378Z",
    "updated_at": "2015-06-15T17:07:42.947Z",
    "status": {
      "approved": false,
      "reason": "No Approved Creatives.  Order expired.  "
    },
    "targeted_creatives": [
      1,
      2,
      3
    ]
  }
]
```

Get all strategies for given advertiser or order or line item or ad.

### Request

`GET /api/strategies?advertiser_id={advertiser_id}&order_id={order_id}&line_item_id={line_item_id}&ad_id={ad_id}`

### Query parameters

Parameter | Description
--------- | -----------
advertiser_id | Advertiser id.
order_id | Order id.
line_item_id | Line item id.
ad_id | Ad id.

## Get single strategy

```shell
curl 'https://toro.collective-media.net/api/strategies/1' \
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
  "name": "Standard",
  "amp_kv": "standard",
  "margin_goal": 11,
  "user_partition": "100.0",
  "budget_partition": "100.0",
  "ramp_end": "0",
  "end_step": "Hours",
  "ramp_begin": "0.5",
  "begin_step": "Hours",
  "min_bid": "0.01",
  "max_cost": "50.0",
  "paused": false,
  "paused_by_parent": false,
  "control_group": false,
  "ad_id": 2,
  "created_at": "2014-07-02T21:00:23.378Z",
  "updated_at": "2015-06-15T17:07:42.947Z",
  "status": {
    "approved": false,
    "reason": "No Approved Creatives.  Order expired.  "
  },
  "targeted_creatives": [
    1,
    2,
    3
  ]
}
```

Get strategy by id.

### Request

`GET /api/strategies/{strategy_id}`

## Create strategy

```shell
curl 'https://toro.collective-media.net/api/strategies' \
  -X POST \
  -H 'Accept: application/json' \
  -H 'Content-type: application/json' \
  -H 'Authorization: Token token="your_api_token"' \
  -d '{"name":"Example.Strategy","amp_kv":"a","margin_goal":10,"user_partition":"100.0","budget_partition":"100.0","max_cost":"50","min_bid":"0.01","ramp_begin":"1","begin_step":"Days","ramp_end":"12","end_step":"Hours","paused":"false","ad_id": 2,"targeted_creatives":[1,2]}'
```

> Response:

```http
HTTP/1.1 201 Created
Content-Type: application/json; charset=utf-8

{
  "id": 59,
  "name": "Example.Strategy",
  "amp_kv": "a",
  "margin_goal": 10,
  "user_partition": "100.0",
  "budget_partition": "100.0",
  "ramp_end": "12",
  "end_step": "Hours",
  "ramp_begin": "1",
  "begin_step": "Day",
  "min_bid": "0.01",
  "max_cost": "50.0",
  "paused": false,
  "paused_by_parent": false,
  "control_group": false,
  "ad_id": 2,
  "created_at": "2015-06-15T17:43:24.562Z",
  "updated_at": "2015-06-15T17:43:24.562Z",
  "status": {
    "approved": false,
    "reason": "No Approved Creatives.  Order expired.  "
  },
  "targeted_creatives": [
    1,
    2
  ]
}
```

Creates strategy.

### Request

`POST /api/strategies`

Field | Default | Description
--------- | ------- | ----------
ad_id | | **[Required]** Ad id.
name | | **[Required]** Strategy name.
amp_kv | | **[Required]** Short name to associate strategy with objects in AMP.
margin_goal | | **[Required]** Desired margin on impressions bought by this strategy. Valid value between 1 and 100
user_partition | | **[Required]** Percentage of users that should see this strategy.
budget_partition | | **[Required]** Percentage of budget should be spent on this strategy.
max_cost | | **[Required]** Maximum amount should be payed to this strategy. This number should be inclusive of any network / serving cost. Value should be greater then 0 and less than equal to 500.
min_bid | | **[Required]** Minimum amount should be payed to show this strategy.
ramp_begin | | **[Required]** The amount of time we should spend ramping back up to maximum weight on a user who has previously seen the associated Ad.
begin_step | | **[Required]** Valid values: 'Days' or 'Hours'
ramp_end | | **[Required]** Time that we should wait before showing user another Ad, if they have just seen one.
end_step | | **[Required]** Valid values: 'Days' or 'Hours'
paused | | Set `true` to create paused strategy.
targeted_creatives | | Array of creative ids.

## Update strategy

```shell
curl 'https://toro.collective-media.net/api/strategies' \
  -X PUT \
  -H 'Accept: application/json' \
  -H 'Content-type: application/json' \
  -H 'Authorization: Token token="your_api_token"' \
  -d '{"amp_kv":"ab","margin_goal":20,"targeted_creatives":[1,2]}'
```

> Response:

```http
HTTP/1.1 200 Ok
Content-Type: application/json; charset=utf-8

{
  "id": 59,
  "name": "Example.Strategy",
  "amp_kv": "ab",
  "margin_goal": 20,
  "user_partition": "100.0",
  "budget_partition": "100.0",
  "ramp_end": "12",
  "end_step": "Hours",
  "ramp_begin": "1",
  "begin_step": "Days",
  "min_bid": "0.01",
  "max_cost": "50.0",
  "paused": false,
  "paused_by_parent": false,
  "control_group": false,
  "ad_id": 2,
  "created_at": "2015-06-15T17:43:24.562Z",
  "updated_at": "2015-06-15T17:43:24.562Z",
  "status": {
    "approved": false,
    "reason": "No Approved Creatives.  Order expired.  "
  },
  "targeted_creatives": [
    1,
    2
  ]
}
```

Updates strategy.

### Request

`PUT /api/strategies/{strategy id}`

Field | Default | Description
--------- | ------- | ----------
name | | Strategy name.
amp_kv | | Short name to associate strategy with objects in AMP.
margin_goal | | Desired margin on impressions bought by this strategy. Valid value between 1 and 100
user_partition | | Percentage of users that should see this strategy.
budget_partition | | Percentage of budget should be spent on this strategy.
max_cost | | Maximum amount should be payed to this strategy. This number should be inclusive of any network / serving cost. Value should be greater then 0 and less than equal to 500.
min_bid | | Minimum amount should be payed to show this strategy.
ramp_begin | | The amount of time we should spend ramping back up to maximum weight on a user who has previously seen the associated Ad.
begin_step | | Valid values: 'Days' or 'Hours'
ramp_end | | Time that we should wait before showing user another Ad, if they have just seen one.
end_step | | Valid values: 'Days' or 'Hours'
paused | | Set `true` to create paused strategy.
targeted_creatives | | Array of creative ids.

## Fields Map

Field | Description
--------- | ----------
name | Strategy name.
amp_kv | Short name to associate strategy with objects in AMP.
margin_goal | Desired margin on impressions bought by this strategy. Valid value between 1 and 100
user_partition | Percentage of users that should see this strategy.
budget_partition | Percentage of budget should be spent on this strategy.
max_cost | Maximum amount should be payed to this strategy. This number should be inclusive of any network / serving cost. Value should be greater then 0 and less than equal to 500.
min_bid | Minimum amount should be payed to show this strategy.
ramp_begin | The amount of time we should spend ramping back up to maximum weight on a user who has previously seen the associated Ad.
begin_step | Valid values: 'Days' or 'Hours'
ramp_end | Time that we should wait before showing user another Ad, if they have just seen one.
end_step | Valid values: 'Days' or 'Hours'
paused | `true` when strategy is paused.
targeted_creatives | Array of associated creative ids.
control_group | if `true`, the user_partition and budget_partition associated with this strategy should be considered a control group
