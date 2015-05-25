# Authentication

> Example API request

```shell
curl 'https://toro.collective-media.net/api/advertisers' \
  -X GET \
  -H 'Accept: application/json' \
  -H 'Content-type: application/json' \
  -H 'Authorization: Token token="your_api_token"'
```


Toro uses API token to authenticate requests. It expects all API requests to include token in request header in following format:

`Authorization: Token token="your_api_token"`

Registered users can get API token by navigating to their profile page in Toro UI.

<aside class="notice">
You must replace `your_api_token` with your personal API token.
</aside>
