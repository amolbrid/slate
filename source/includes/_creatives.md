# Creatives

## Fields Guide

Field | Description
--------- | -----------
id | Creative id
name | Name of the creative.
size | Creative size
zone | Zone associated with creative
advertiser_id | Advertiser associated with creative
appnexus_id | Associated appnexus id
iframe_url | creative url
is_expired | True if creative is expired. otherwise false
submitted_to_appnexus | true when creative is submitted to appnexus for auditing. Otherwise false.
audit_status | Creative audit status. Possible values: "pending", "audited" and "rejected".
audit_feedback | If creative is rejected, this will contain the reason  rejection.
ssl_audit_status | Audit status of ssl creative
tracking_pixels | Tracking pixel associated with creative

## Get all creatives


```shell
curl 'https://toro.collective-media.net/api/creatives?advertiser_id=2' \
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
    "id": 113,
    "name": "Disney | 728x90 | 1.75",
    "size": "728x90",
    "zone": "1.75",
    "advertiser_id": 2,
    "created_at": "2014-06-30T17:30:25.747Z",
    "updated_at": "2014-07-28T15:40:30.636Z",
    "appnexus_id": "16822724",
    "submitted_to_appnexus": true,
    "is_expired": false,
    "audit_status": "rejected",
    "ssl_audit_status": null,
    "audit_feedback": "Creative does not display properly",
    "iframe_url": "http://a.collective-media.net/adi/cm.proga/1.75;sz=728x90;tgt=1.75${STRATEGY_TGT};st_id=${STRATEGY_ID};auc_id=${AUCTION_ID};axi=${USER_ID};xcamp=${PUBLISHER_ID};xchan=${SELLER_MEMBER_ID};xurl=${REFERER_URL_ENC};click=${CLICK_URL};ord=${CACHEBUSTER};segs=${SEGMENT_TGT};",
    "tracking_pixels": []
  },
  {
    "id": 14,
    "name": "Disney | 728x90 | disney_dmx_cpa",
    "size": "728x90",
    "zone": "disney_dmx_cpa",
    "advertiser_id": 2,
    "created_at": "2014-03-27T18:35:11.846Z",
    "updated_at": "2014-07-28T15:34:37.045Z",
    "appnexus_id": "13858138",
    "submitted_to_appnexus": true,
    "is_expired": false,
    "audit_status": "audited",
    "ssl_audit_status": null,
    "audit_feedback": "",
    "iframe_url": "http://a.collective-media.net/adi/cm.proga/disney_dmx_cpa;sz=728x90;tgt=disney_dmx_cpa${STRATEGY_TGT};st_id=${STRATEGY_ID};auc_id=${AUCTION_ID};axi=${USER_ID};xcamp=${PUBLISHER_ID};xchan=${SELLER_MEMBER_ID};xurl=${REFERER_URL_ENC};click=${CLICK_URL};ord=${CACHEBUSTER};segs=${SEGMENT_TGT};",
    "tracking_pixels": []
  }
]

```

List all creatives for advertiser

### Request

`GET /api/creatives?advertiser_id={advertiser_id}`

### Query parameters

Parameter | Description
--------- | -----------
advertiser_id | **[Required]** Advertiser id.


## Get single creative

```shell
curl 'https://toro.collective-media.net/api/creatives/14' \
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
  "id": 14,
  "name": "Disney | 728x90 | disney_dmx_cpa",
  "size": "728x90",
  "zone": "disney_dmx_cpa",
  "advertiser_id": 2,
  "created_at": "2014-03-27T18:35:11.846Z",
  "updated_at": "2014-07-28T15:34:37.045Z",
  "appnexus_id": "13858138",
  "submitted_to_appnexus": true,
  "is_expired": false,
  "audit_status": "audited",
  "ssl_audit_status": null,
  "audit_feedback": "",
  "iframe_url": "http://a.collective-media.net/adi/cm.proga/disney_dmx_cpa;sz=728x90;tgt=disney_dmx_cpa${STRATEGY_TGT};st_id=${STRATEGY_ID};auc_id=${AUCTION_ID};axi=${USER_ID};xcamp=${PUBLISHER_ID};xchan=${SELLER_MEMBER_ID};xurl=${REFERER_URL_ENC};click=${CLICK_URL};ord=${CACHEBUSTER};segs=${SEGMENT_TGT};",
  "tracking_pixels": []

}
```

Gets creative by id

### Request

`GET /api/creatives/{creative_id}`


## Create creative

```shell
curl 'https://toro.collective-media.net/api/creatives' \
  -X POST \
  -H 'Accept: application/json' \
  -H 'Content-type: application/json' \
  -H 'Authorization: Token token="your_api_token"' \
  -d '{"name":"Test creative", "size":["160x600"], "zone":"test.zone", "advertiser_id":2}'
```

> Response:

```http
HTTP/1.1 201 Created
Content-Type: application/json; charset=utf-8

[
  {
    "id": 599,
    "name": "Test creative | 160x600 | test.zone",
    "size": "160x600",
    "zone": "test.zone",
    "advertiser_id": 2,
    "created_at": "2015-05-22T14:31:58.040Z",
    "updated_at": "2015-05-22T14:31:58.040Z",
    "appnexus_id": null,
    "submitted_to_appnexus": false,
    "is_expired": false,
    "audit_status": null,
    "ssl_audit_status": null,
    "audit_feedback": null,
    "iframe_url": "http://a.collective-media.net/adi/cm.proga/test.zone;sz=160x600;tgt=test.zone${STRATEGY_TGT};st_id=${STRATEGY_ID};auc_id=${AUCTION_ID};axi=${USER_ID};xcamp=${PUBLISHER_ID};xchan=${SELLER_MEMBER_ID};xurl=${REFERER_URL_ENC};click=${CLICK_URL};ord=${CACHEBUSTER};segs=${SEGMENT_TGT};",
    "tracking_pixels": []
  }
]
```

Creates one or more creatives.

### Request

`POST /api/creatives`

Field | Default | Description
--------- | ------- | -----------
name | | **[Required]** Creative name. Should be unique.
size | | **[Required]** Array of ad sizes. Creatives are created for each ad size. So if there are two ad sizes, "160x600" and "300x250", two creatives will be created. One with ad size "160x600" and other with ad size "300x250".
zone | | **[Required]** Zone associated with creative
advertiser_id | | **[Required]** Advertiser id
tracking_pixel | | Array of tracking pixel associated with creative.

#### Tracking pixel
Field | Description
------ | -----------
format | **[Required]** Pixel format. Valid values: "url-html", "url-js", "url-image" or "raw-url"
url | **[Required]** Pixel url


## Update creative

```shell
curl 'https://toro.collective-media.net/api/creatives/599' \
  -X PUT \
  -H 'Accept: application/json' \
  -H 'Content-type: application/json' \
  -H 'Authorization: Token token="your_api_token"' \
  -d '{"zone":"new.zone"}'
```

> Response:

```http
HTTP/1.1 200 Ok
Content-Type: application/json; charset=utf-8

{
  "id": 599,
  "name": "Test creative | 160x600 | test.zone",
  "size": "160x600",
  "zone": "new.zone",
  "advertiser_id": 2,
  "created_at": "2015-05-22T14:31:58.040Z",
  "updated_at": "2015-05-22T14:58:43.819Z",
  "appnexus_id": null,
  "submitted_to_appnexus": false,
  "is_expired": false,
  "audit_status": null,
  "ssl_audit_status": null,
  "audit_feedback": null,
  "iframe_url": "http://a.collective-media.net/adi/cm.proga/new.zone;sz=160x600;tgt=new.zone${STRATEGY_TGT};st_id=${STRATEGY_ID};auc_id=${AUCTION_ID};axi=${USER_ID};xcamp=${PUBLISHER_ID};xchan=${SELLER_MEMBER_ID};xurl=${REFERER_URL_ENC};click=${CLICK_URL};ord=${CACHEBUSTER};segs=${SEGMENT_TGT};",
  "tracking_pixels": [ ]
}
```

Updates creative

### Request

`PUT /api/creatives/{creative_id}`

Field | Default | Description
--------- | ------- | -----------
name | | Creative name. Should be unique.
size | | Ad size.
zone | | Zone associated with creative
