# TrackerEntry object

## Fields

| Field | Type | Description | Editable |
| :--- | :--- | :--- | :--- |
| time_unix | integer |  |  |
| payload | object |  |  |
| user_uuid | string |  |  |
| t | integer |  |  |
| ua | string |  |  |
| p | string |  |  |
| r | string |  |  |
| l | string |  |  |
| tz | string |  |  |

## Filters

| Field | Description |
| :--- | :--- |
| user_uuid |  |

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/123e52529e9ffdabe8cb)

{% api-method method="get" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/tracker_entries" %}
{% api-method-summary %}
search tracker entries
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="X-Access-Token" type="string" required=true %}
set you access token
{% endapi-method-parameter %}

{% api-method-parameter name="Content-Type" type="string" required=true %}
application/vnd.api+json
{% endapi-method-parameter %}

{% api-method-parameter name="Accept" type="string" required=true %}
application/vnd.api+json
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
  "data": [
    {
      "id": "1",
      "type": "tracker_entries",
      "links": {
        "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/tracker_entries/1"
      },
      "attributes": {
        "time_unix": 1542602846,
        "payload": {
          "ua": "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_1) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/70.0.3538.102 Safari/537.36",
          "p": "MacIntel",
          "r": "",
          "l": "https://{YOUR_OKSKY_DOMAIN}/clients/1/test",
          "t": 1542602846433,
          "tz": "Asia/Tokyo"
        },
        "user_uuid": "93ac8829-55c4-43bf-ae8c-a3c646110765",
        "t": 1542602846433,
        "ua": "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_1) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/70.0.3538.102 Safari/537.36",
        "p": "MacIntel",
        "r": "",
        "l": "https://{YOUR_OKSKY_DOMAIN}/clients/1/test",
        "tz": "Asia/Tokyo"
      }
    }
  ],
  "meta": {
    "record_count": 1
  },
  "links": {
    "first": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/tracker_entries?page%5Bnumber%5D=1&page%5Bsize%5D=25",
    "last": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/tracker_entries?page%5Bnumber%5D=1&page%5Bsize%5D=25"
  }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/tracker_entries/latest_for_user_uuid" %}
{% api-method-summary %}
latest for user uuid
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="X-Access-Token" type="string" required=true %}
set you access token
{% endapi-method-parameter %}

{% api-method-parameter name="Content-Type" type="string" required=true %}
application/vnd.api+json
{% endapi-method-parameter %}

{% api-method-parameter name="Accept" type="string" required=true %}
application/vnd.api+json
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
  "data": {
    "id": "1",
    "type": "tracker_entries",
    "links": {
      "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/tracker_entries/1"
    },
    "attributes": {
      "time_unix": 1542602846,
      "payload": {
        "ua": "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_1) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/70.0.3538.102 Safari/537.36",
        "p": "MacIntel",
        "r": "",
        "l": "https://{YOUR_OKSKY_DOMAIN}/clients/1/test",
        "t": 1542602846433,
        "tz": "Asia/Tokyo"
      },
      "user_uuid": "93ac8829-55c4-43bf-ae8c-a3c646110765",
      "t": 1542602846433,
      "ua": "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_1) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/70.0.3538.102 Safari/537.36",
      "p": "MacIntel",
      "r": "",
      "l": "https://{YOUR_OKSKY_DOMAIN}/clients/1/test",
      "tz": "Asia/Tokyo"
    }
  }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}
