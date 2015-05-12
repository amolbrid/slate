# Creatives

## Get all creatives

```ruby
# ruby code here
```

```scala
// scala code here
```


```shell
curl 'https://toro.collective-media.net/api/creatives?advertiser_id=2' \
  -X GET \
  -H 'Accept: application/json' \
  -H 'Content-type: application/json' \
  -H 'Authorization: Token token="your_api_token"'
```



> Response

```json
[
  {
    "id": 112,
    "name": "Disney | 160x600 | 1.75",
    "size": "160x600",
    "zone": "1.75",
    "created_at": "2014-06-30T17:30:25.732Z",
    "updated_at": "2014-07-28T15:40:28.980Z",
    "iframe_url": "http://a.collective-media.net/adi/cm.proga/1.75;sz=160x600;tgt=1.75${STRATEGY_TGT};st_id=${STRATEGY_ID};auc_id=${AUCTION_ID};axi=${USER_ID};xcamp=${PUBLISHER_ID};xchan=${SELLER_MEMBER_ID};xurl=${REFERER_URL_ENC};click=${CLICK_URL};ord=${CACHEBUSTER};segs=${SEGMENT_TGT};",
    "is_can_be_dissociate": false,
    "audit": {
      "status": "rejected",
      "ssl_status": null,
      "response": "Creative does not display properly"
    },
    "appnexus": {
      "id": "16822718",
      "submitted": true,
      "status": "rejected",
      "expired": false
    }
  },
  {
    "id": 13,
    "name": "Disney | 160x600 | disney_dmx_cpa",
    "size": "160x600",
    "zone": "disney_dmx_cpa",
    "created_at": "2014-03-27T18:35:11.837Z",
    "updated_at": "2014-07-28T15:34:50.403Z",
    "iframe_url": "http://a.collective-media.net/adi/cm.proga/disney_dmx_cpa;sz=160x600;tgt=disney_dmx_cpa${STRATEGY_TGT};st_id=${STRATEGY_ID};auc_id=${AUCTION_ID};axi=${USER_ID};xcamp=${PUBLISHER_ID};xchan=${SELLER_MEMBER_ID};xurl=${REFERER_URL_ENC};click=${CLICK_URL};ord=${CACHEBUSTER};segs=${SEGMENT_TGT};",
    "is_can_be_dissociate": true,
    "audit": {
      "status": "audited",
      "ssl_status": null,
      "response": ""
    },
    "appnexus": {
      "id": "13858137",
      "submitted": true,
      "status": "audited",
      "expired": false
    }
  }
]
```

List all creatives for advertiser

### Request

`GET https://toro.collective-media.net/api/creatives?advertiser_id={advertiser_id}`

### Query parameters

Parameter | Description
--------- | -----------
advertiser_id | **[Required]** Advertiser id.

### Response

Field | Description
--------- | -----------
id | Creative id
name | Name of the creative.
size | Creative size
zone | Zone associated with creative


##### Appnexus Fields

Field | Description
--------- | -----------
id | Associated appnexus creative id
submitted | Creative submitted for audit
status | Audited status of creative in appnexus
expired | Whether creative is expired

##### Audit Fields

Field | Description
--------- | -----------
status | Audit status of creative
ssl_status | SSL audit status of creative
response | Error message returned by Appnexus when audit fails.

## Get single creative

```ruby
# ruby code here
```

```scala
// scala code here
```

```shell
curl 'https://toro.collective-media.net/api/creatives/234' \
  -X GET \
  -H 'Accept: application/json' \
  -H 'Content-type: application/json' \
  -H 'Authorization: Token token="your_api_token"'
```

> Response

```json
{
  "id": 234,
  "name": "RON Disney | 300x250 | dny_domcom_1_new",
  "size": "300x250",
  "zone": "dny_domcom_1_new",
  "created_at": "2014-07-02T22:20:53.208Z",
  "updated_at": "2014-07-28T15:40:59.219Z",
  "iframe_url": "http://a.collective-media.net/adi/cm.proga/dny_domcom_1_new;sz=300x250;tgt=dny_domcom_1_new${STRATEGY_TGT};st_id=${STRATEGY_ID};auc_id=${AUCTION_ID};axi=${USER_ID};xcamp=${PUBLISHER_ID};xchan=${SELLER_MEMBER_ID};xurl=${REFERER_URL_ENC};click=${CLICK_URL};ord=${CACHEBUSTER};segs=${SEGMENT_TGT};",
  "is_can_be_dissociate": true,
  "audit": {
    "status": "audited",
    "ssl_status": null,
    "response": ""
  },
  "appnexus": {
    "id": "16943312",
    "submitted": true,
    "status": "audited",
    "expired": false
  }
}
```

Gets creative by id

### Request

`GET https://toro.collective-media.net/api/creatives/{creative_id}`

### Response

Field | Description
--------- | -----------
id | Creative id
name | Name of the creative.
size | Creative size
zone | Zone associated with creative
