# UserEvent object

## Fields

| Field | Type | Description | Editable |
| :--- | :--- | :--- | :--- |
| resource\_type | string |  |  |
| kind | string |  |  |
| resource\_id | integer |  |  |
| created\_at\_unix | integer |  |  |

## Filters

| Field | Description |
| :--- | :--- |
| id | ID |

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/20b7f3930eb31c9ebf89)

{% api-method method="get" host="" path="https://{YOUR\_OKSKY\_DOMAIN}/rapi/v1/user\_events/{:id}" %}
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

{
  "data": {
    "id": "1",
    "type": "user_events",
    "links": {
      "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/user_events/1"
    },
    "attributes": {
      "resource_type": null,
      "kind": "signin",
      "resource_id": null,
      "created_at_unix": 1542602792
    },
    "relationships": {
      "user": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/user_events/1/relationships/user",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/user_events/1/user"
        },
        "data": {
          "type": "users",
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

{% api-method method="get" host="" path="https://{YOUR\_OKSKY\_DOMAIN}/rapi/v1/user\_events" %}
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
      "links": {
        "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/user_events/1"
      },
      "attributes": {
        "resource_type": null,
        "kind": "signin",
        "resource_id": null,
        "created_at_unix": 1542602792
      },
      "relationships": {
        "user": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/user_events/1/relationships/user",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/user_events/1/user"
          },
          "data": {
            "type": "users",
            "id": "1"
          }
        }
      }
    },
    {
      "id": "2",
      "type": "user_events",
      "links": {
        "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/user_events/2"
      },
      "attributes": {
        "resource_type": null,
        "kind": "signin",
        "resource_id": null,
        "created_at_unix": 1542602846
      },
      "relationships": {
        "user": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/user_events/2/relationships/user",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/user_events/2/user"
          },
          "data": {
            "type": "users",
            "id": "2"
          }
        }
      }
    },
    {
      "id": "3",
      "type": "user_events",
      "links": {
        "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/user_events/3"
      },
      "attributes": {
        "resource_type": "Room",
        "kind": "obj_create",
        "resource_id": 1,
        "created_at_unix": 1542602860
      },
      "relationships": {
        "user": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/user_events/3/relationships/user",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/user_events/3/user"
          },
          "data": {
            "type": "users",
            "id": "2"
          }
        }
      }
    }
  ],
  "meta": {
    "record_count": 3
  },
  "links": {
    "first": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/user_events?page%5Bnumber%5D=1&page%5Bsize%5D=25",
    "last": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/user_events?page%5Bnumber%5D=1&page%5Bsize%5D=25"
  }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

