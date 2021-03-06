# Suggestion object

## Fields

| Field | Type | Description | Editable |
| :--- | :--- | :--- | :--- |
| suggestion\_messages\_data | array |  |  |

## Filters

| Field | Description |
| :--- | :--- |
| id | ID |
| room\_id | RoomのID |

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/981e77b11762be50c5d9)

{% api-method method="get" host="" path="https://{YOUR\_OKSKY\_DOMAIN}/rapi/v1/suggestions/{:id}" %}
{% api-method-summary %}
find suggestion
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

{
  "data": {
    "id": "1",
    "type": "suggestions",
    "links": {
      "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/suggestions/1"
    },
    "attributes": {
      "suggestion_messages_data": [
        {
          "kind": "text",
          "content": "Content",
          "settings": {}
        }
      ]
    },
    "relationships": {
      "room": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/suggestions/1/relationships/room",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/suggestions/1/room"
        },
        "data": {
          "type": "rooms",
          "id": "1"
        }
      }
    }
  }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="" path="https://{YOUR\_OKSKY\_DOMAIN}/rapi/v1/suggestions" %}
{% api-method-summary %}
search suggestions
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
      "type": "suggestions",
      "links": {
        "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/suggestions/1"
      },
      "attributes": {
        "suggestion_messages_data": [
          {
            "kind": "text",
            "content": "Content",
            "settings": {}
          }
        ]
      },
      "relationships": {
        "room": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/suggestions/1/relationships/room",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/suggestions/1/room"
          },
          "data": {
            "type": "rooms",
            "id": "1"
          }
        }
      }
    }
  ],
  "meta": {
    "record_count": 1
  },
  "links": {
    "first": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/suggestions?page%5Bnumber%5D=1&page%5Bsize%5D=25",
    "last": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/suggestions?page%5Bnumber%5D=1&page%5Bsize%5D=25"
  }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="" path="https://{YOUR\_OKSKY\_DOMAIN}/rapi/v1/suggestions" %}
{% api-method-summary %}
create suggestion
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Accept" type="string" required=false %}
application/vnd.api+json
{% endapi-method-parameter %}

{% api-method-parameter name="Content-Type" type="string" required=true %}
application/vnd.api+json
{% endapi-method-parameter %}

{% api-method-parameter name="X-Access-Token" type="string" required=true %}
set your access token
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="data" type="object" required=true %}

{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
  "data": {
    "id": "1",
    "type": "suggestions",
    "links": {
      "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/suggestions/1"
    },
    "attributes": {
      "suggestion_messages_data": [
        {
          "kind": "text",
          "content": "test"
        }
      ]
    },
    "relationships": {
      "room": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/suggestions/1/relationships/room",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/suggestions/1/room"
        },
        "data": {
          "type": "rooms",
          "id": "1"
        }
      }
    }
  }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="put" host="" path="https://{YOUR\_OKSKY\_DOMAIN}/rapi/v1/suggestions/{:id}" %}
{% api-method-summary %}
update suggestions
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

{% api-method-body-parameters %}
{% api-method-parameter name="data" type="object" required=true %}

{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
  "data": {
    "id": "1",
    "type": "suggestions",
    "links": {
      "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/suggestions/1"
    },
    "attributes": {
      "suggestion_messages_data": [
        {
          "kind": "text",
          "content": "test"
        }
      ]
    },
    "relationships": {
      "room": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/suggestions/1/relationships/room",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/suggestions/1/room"
        },
        "data": {
          "type": "rooms",
          "id": "1"
        }
      }
    }
  }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="delete" host="" path="https://{YOUR\_OKSKY\_DOMAIN}/rapi/v1/suggestions/{:id}" %}
{% api-method-summary %}
delete suggestion
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
{% api-method-response-example httpCode=204 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
Completed 204 No Content
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

