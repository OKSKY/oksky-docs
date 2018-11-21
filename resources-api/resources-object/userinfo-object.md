# UserInfo object

## Fields

| Field | Type | Description | Editable |
| :--- | :--- | :--- | :--- |
| value_data | string |  |  |

## Filters

| Field | Description |
| :--- | :--- |
| id | ID |

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/d5764fee0f296fb30cad)

{% api-method method="get" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/user_infos/{:id}" %}
{% api-method-summary %}
find user info
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
    "type": "user_infos",
    "links": {
      "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/user_infos/1"
    },
    "attributes": {
      "value_data": "1234"
    },
    "relationships": {
      "user": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/user_infos/1/relationships/user",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/user_infos/1/user"
        },
        "data": {
          "type": "users",
          "id": "2"
        }
      },
      "master_keyword": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/user_infos/1/relationships/master_keyword",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/user_infos/1/master_keyword"
        },
        "data": {
          "type": "master_keywords",
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

{% api-method method="get" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/user_infos" %}
{% api-method-summary %}
search user infos
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
      "type": "user_infos",
      "links": {
        "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/user_infos/1"
      },
      "attributes": {
        "value_data": "1234"
      },
      "relationships": {
        "user": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/user_infos/1/relationships/user",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/user_infos/1/user"
          },
          "data": {
            "type": "users",
            "id": "2"
          }
        },
        "master_keyword": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/user_infos/1/relationships/master_keyword",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/user_infos/1/master_keyword"
          },
          "data": {
            "type": "master_keywords",
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
    "first": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/user_infos?page%5Bnumber%5D=1&page%5Bsize%5D=25",
    "last": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/user_infos?page%5Bnumber%5D=1&page%5Bsize%5D=25"
  }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/user_infos" %}
{% api-method-summary %}
create user info
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
    "type": "user_infos",
    "links": {
      "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/user_infos/2"
    },
    "attributes": {
      "value_data": null
    },
    "relationships": {
      "user": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/user_infos/2/relationships/user",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/user_infos/2/user"
        },
        "data": null
      },
      "master_keyword": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/user_infos/2/relationships/master_keyword",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/user_infos/2/master_keyword"
        },
        "data": {
          "type": "master_keywords",
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

{% api-method method="put" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/user_infos/{:id}" %}
{% api-method-summary %}
update user infos
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
    "type": "user_infos",
    "links": {
      "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/user_infos/1"
    },
    "attributes": {
      "value_data": "1234"
    },
    "relationships": {
      "user": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/user_infos/1/relationships/user",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/user_infos/1/user"
        },
        "data": {
          "type": "users",
          "id": "2"
        }
      },
      "master_keyword": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/user_infos/1/relationships/master_keyword",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/user_infos/1/master_keyword"
        },
        "data": {
          "type": "master_keywords",
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

{% api-method method="delete" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/user_infos/{:id}" %}
{% api-method-summary %}
delete user info
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

```
Completed 204 No Content
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}
