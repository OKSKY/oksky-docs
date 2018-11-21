# MasterKeyword object

## Fields

| Field | Type | Description | Editable |
| :--- | :--- | :--- | :--- |
| key_name | string |  |
| key_title | string |  |
| suggestions | string |  |

## Filters

| Field | Description |
| :--- | :--- |
| id | ID |

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/a7d848e84131d1179d8e)

{% api-method method="get" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/master_keywords/{:id}" %}
{% api-method-summary %}
find master keyword
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
    "type": "master_keywords",
    "links": {
      "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/master_keywords/1"
    },
    "attributes": {
      "key_name": "customer_code",
      "key_title": "",
      "suggestions": [
        "1234"
      ]
    },
    "relationships": {
      "user_infos": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/master_keywords/1/relationships/user_infos",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/master_keywords/1/user_infos"
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

{% api-method method="get" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/master_keywords" %}
{% api-method-summary %}
search master keywords
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
      "type": "master_keywords",
      "links": {
        "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/master_keywords/1"
      },
      "attributes": {
        "key_name": "customer_code",
        "key_title": "",
        "suggestions": [
          "1234"
        ]
      },
      "relationships": {
        "user_infos": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/master_keywords/1/relationships/user_infos",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/master_keywords/1/user_infos"
          }
        }
      }
    }
  ],
  "meta": {
    "record_count": 1
  },
  "links": {
    "first": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/master_keywords?page%5Bnumber%5D=1&page%5Bsize%5D=25",
    "last": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/master_keywords?page%5Bnumber%5D=1&page%5Bsize%5D=25"
  }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/master_keywords" %}
{% api-method-summary %}
create master keyword
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
    "type": "master_keywords",
    "links": {
      "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/master_keywords/2"
    },
    "attributes": {
      "key_name": "login_key",
      "key_title": "",
      "suggestions": []
    },
    "relationships": {
      "user_infos": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/master_keywords/2/relationships/user_infos",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/master_keywords/2/user_infos"
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

{% api-method method="put" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/master_keywords/{:id}" %}
{% api-method-summary %}
update master keywords
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
    "id": "1",
    "type": "master_keywords",
    "links": {
      "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/master_keywords/1"
    },
    "attributes": {
      "key_name": "customer_code",
      "key_title": "",
      "suggestions": [
        "1234"
      ]
    },
    "relationships": {
      "user_infos": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/master_keywords/1/relationships/user_infos",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/master_keywords/1/user_infos"
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

{% api-method method="delete" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/master_keywords/{:id}" %}
{% api-method-summary %}
delete master keyword
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
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=204 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
Completed 204 No Content
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}
