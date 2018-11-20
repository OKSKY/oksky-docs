# Memo object

## Fields

| Field | Type | Description | Editable |
| :--- | :--- | :--- | :--- |
| resource_id | integer |  |  |
| resource_type | string |  |  |
| user_id | integer |  |  |
| text | string |  |  |
| created_at_unix | integer |  |  |

## Filters

| Field | Description |
| :--- | :--- |

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/6cc5fa81ae1644800b7d)

{% api-method method="get" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/memos/{:id}" %}
{% api-method-summary %}
find memo
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
    "type": "memos",
    "links": {
      "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/memos/1"
    },
    "attributes": {
      "resource_id": 1,
      "resource_type": "Room",
      "user_id": 1,
      "text": "Memo",
      "created_at_unix": 1542679299
    },
    "relationships": {
      "user": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/memos/1/relationships/user",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/memos/1/user"
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

{% api-method method="get" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/memos" %}
{% api-method-summary %}
search memos
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
      "type": "memos",
      "links": {
        "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/memos/1"
      },
      "attributes": {
        "resource_id": 1,
        "resource_type": "Room",
        "user_id": 1,
        "text": "Memo",
        "created_at_unix": 1542679299
      },
      "relationships": {
        "user": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/memos/1/relationships/user",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/memos/1/user"
          },
          "data": {
            "type": "users",
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
    "first": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/memos?page%5Bnumber%5D=1&page%5Bsize%5D=25",
    "last": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/memos?page%5Bnumber%5D=1&page%5Bsize%5D=25"
  }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/memos" %}
{% api-method-summary %}
create memo
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

```
{
  "data": {
    "id": "2",
    "type": "memos",
    "links": {
      "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/memos/2"
    },
    "attributes": {
      "resource_id": 1,
      "resource_type": "Room",
      "user_id": 1,
      "text": null,
      "created_at_unix": 1542679363
    },
    "relationships": {
      "user": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/memos/2/relationships/user",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/memos/2/user"
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

{% api-method method="put" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/memos/{:id}" %}
{% api-method-summary %}
update memos
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

```
{
  "data": {
    "id": "1",
    "type": "memos",
    "links": {
      "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/memos/1"
    },
    "attributes": {
      "resource_id": 1,
      "resource_type": "Room",
      "user_id": 1,
      "text": "Memo",
      "created_at_unix": 1542679299
    },
    "relationships": {
      "user": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/memos/1/relationships/user",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/memos/1/user"
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

{% api-method method="delete" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/memos/{:id}" %}
{% api-method-summary %}
delete memo
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

```
Completed 204 No Content
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}
