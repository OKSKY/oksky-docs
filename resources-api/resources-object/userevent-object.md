# UserEvent object

## Fields

| Field | Type | Description | Editable |
| :--- | :--- | :--- | :--- |
| resource_type | string |  |  |
| kind | string |  |  |
| resource_id | integer |  |  |
| created_at_unix | integer |  |  |

## Filters

| Field | Description |
| :--- | :--- |

{% api-method method="get" host="" path="/rapi/v1/user_events/{:id}" %}
{% api-method-summary %}
find user event
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
HTTP/1.1 200 OK
Content-Type: application/vnd.api+json

{"data": {"id": "1", "type": "user_events", "links": {...}, "attributes": {...}, "relationships": {...}}}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="" path="/rapi/v1/user_events" %}
{% api-method-summary %}
search user events
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
      "type": "user_events",
      "links": {...},
      "attributes": {...},
      "relationships": {...}
    }
  ],
  "meta": {
    "record_count": 1
  },
  "links": {...}
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}
