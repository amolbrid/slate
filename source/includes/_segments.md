# Segments

## Search segments

```shell
curl 'https://toro.collective-media.net/api/segments/search?search=aal' \
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
    "id": 6332,
    "name": "Branded : TVAA : Q4 2012 : Discovery Channel : Prime (8pm-11pm)_H",
    "code": "vs.aal",
    "shared": false,
    "targeting_enabled": false,
    "amts_id": 65912,
    "appnexus_id": null,
    "appnexus_member_id": null,
    "created_at": "2014-10-15T14:01:35.941Z",
    "updated_at": "2014-10-15T14:01:35.941Z"
  },
  {
    "id": 12130,
    "name": "Psychographic : Interest : Social : Video Engagers",
    "code": "ad.aal",
    "shared": false,
    "targeting_enabled": false,
    "amts_id": 76581,
    "appnexus_id": null,
    "appnexus_member_id": null,
    "created_at": "2014-10-15T14:02:09.846Z",
    "updated_at": "2014-10-15T14:02:09.846Z"
  }
]
```

Search segments by name/code, shared and targeting status

### Request

`GET /api/segments/search?search={name|code}&shared={true|false}&targeting_enabled={true|false}`

### Query parameters

Parameter | Description
--------- | -----------
search | filter by matching name or code
shared | filter by shared status
targeting_enabled | filter by whether segment is enabled for targeting or not.

## Create segment

```shell
curl 'https://toro.collective-media.net/api/segments' \
  -X POST \
  -H 'Accept: application/json' \
  -H 'Content-type: application/json' \
  -H 'Authorization: Token token="your_api_token"' \
  -d '{"name": "Test segment", "code": "test.seg"}'
```

> Response:

```http
HTTP/1.1 201 Created
Content-Type: application/json; charset=utf-8

{
  "id": 12131,
  "name": "Test segment",
  "code": "test.seg",
  "shared": false,
  "targeting_enabled": false,
  "amts_id": null,
  "appnexus_id": null,
  "appnexus_member_id": null,
  "created_at": "2014-10-15T14:02:09.846Z",
  "updated_at": "2014-10-15T14:02:09.846Z"
}
```

### Request

`POST /api/segments`

Field | Default | Description
--------- | ------- | -----------
name |  | **[Required]** Name of the segment
code | | Unique segment code.
amts_id | | Amts id if segment is present in AMTS.

## Update segment

```shell
curl 'https://toro.collective-media.net/api/segments/12131' \
  -X PUT \
  -H 'Accept: application/json' \
  -H 'Content-type: application/json' \
  -H 'Authorization: Token token="your_api_token"' \
  -d '{"name":"Test segment update", "shared":true}'
```

> Response:

```http
HTTP/1.1 200 Ok
Content-Type: application/json; charset=utf-8

{
  "id": 12131,
  "name": "Test segment update",
  "code": "test.seg",
  "shared": false,
  "targeting_enabled": false,
  "amts_id": null,
  "appnexus_id": 23465,
  "appnexus_member_id": 1234,
  "created_at": "2014-10-15T14:02:09.846Z",
  "updated_at": "2014-10-15T14:02:09.846Z"
}
```

Updates segment.

### Request

`PUT /api/segments/{segment_id}`

Field | Default | Description
--------- | ------- | -----------
name |  | Name of the segment.
code | | Unique segment code.
shared | | Set `true` to share segment with Appnexus.
targeting_enabled | | Set `true` to enable segment for targeting.

## Fields Guide

Field | Description
--------- | -----------
id | Segment id.
name | Name of the segment.
code | Unique segment code.
shared | `true` when segment is shared with Appnexus.
targeting_enabled | `true` to enable segment for targeting. Segment should also be shared.
amts_id | Amts id of segment.
appnexus_id | Appnexus id of segment.
appnexus_member_id | Appnexus member id.
