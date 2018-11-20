# Member object

## Fields

| Field | Type | Description | Editable |
| :--- | :--- | :--- | :--- |
| last_read_at_unix | integer |  |  |
| unread_message_count | integer |  |  |
| is_room_visible | boolean |  |  |
| user_typing | string |  |  |

## Filters

| Field | Description |
| :--- | :--- |
| room_id |  |
| user_id |  |

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/4a557e89a56ea430647b)

{% api-method method="get" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/{:id}" %}
{% api-method-summary %}
find member
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
    "type": "members",
    "links": {
      "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/1"
    },
    "attributes": {
      "last_read_at_unix": 1542602860,
      "unread_message_count": 1,
      "is_room_visible": true,
      "user_typing": null
    },
    "relationships": {
      "room": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/1/relationships/room",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/1/room"
        },
        "data": {
          "type": "rooms",
          "id": "1"
        }
      },
      "user": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/1/relationships/user",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/1/user"
        },
        "data": {
          "type": "users",
          "id": "2"
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

{% api-method method="get" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members" %}
{% api-method-summary %}
search members
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
{
  "data": [
    {
      "id": "1",
      "type": "members",
      "links": {
        "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/1"
      },
      "attributes": {
        "last_read_at_unix": 1542602860,
        "unread_message_count": 1,
        "is_room_visible": true,
        "user_typing": null
      },
      "relationships": {
        "room": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/1/relationships/room",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/1/room"
          },
          "data": {
            "type": "rooms",
            "id": "1"
          }
        },
        "user": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/1/relationships/user",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/1/user"
          },
          "data": {
            "type": "users",
            "id": "2"
          }
        }
      }
    },
    {
      "id": "2",
      "type": "members",
      "links": {
        "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/2"
      },
      "attributes": {
        "last_read_at_unix": 0,
        "unread_message_count": 0,
        "is_room_visible": false,
        "user_typing": null
      },
      "relationships": {
        "room": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/2/relationships/room",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/2/room"
          },
          "data": {
            "type": "rooms",
            "id": "3"
          }
        },
        "user": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/2/relationships/user",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/2/user"
          },
          "data": {
            "type": "users",
            "id": "1"
          }
        }
      }
    },
    {
      "id": "3",
      "type": "members",
      "links": {
        "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/3"
      },
      "attributes": {
        "last_read_at_unix": 0,
        "unread_message_count": 1,
        "is_room_visible": false,
        "user_typing": null
      },
      "relationships": {
        "room": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/3/relationships/room",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/3/room"
          },
          "data": {
            "type": "rooms",
            "id": "1"
          }
        },
        "user": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/3/relationships/user",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/3/user"
          },
          "data": {
            "type": "users",
            "id": "1"
          }
        }
      }
    },
    {
      "id": "5",
      "type": "members",
      "links": {
        "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/5"
      },
      "attributes": {
        "last_read_at_unix": 0,
        "unread_message_count": 0,
        "is_room_visible": false,
        "user_typing": null
      },
      "relationships": {
        "room": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/5/relationships/room",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/5/room"
          },
          "data": {
            "type": "rooms",
            "id": "5"
          }
        },
        "user": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/5/relationships/user",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/5/user"
          },
          "data": {
            "type": "users",
            "id": "1"
          }
        }
      }
    },
    {
      "id": "6",
      "type": "members",
      "links": {
        "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/6"
      },
      "attributes": {
        "last_read_at_unix": 0,
        "unread_message_count": 1,
        "is_room_visible": true,
        "user_typing": null
      },
      "relationships": {
        "room": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/6/relationships/room",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/6/room"
          },
          "data": {
            "type": "rooms",
            "id": "6"
          }
        },
        "user": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/6/relationships/user",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/6/user"
          },
          "data": {
            "type": "users",
            "id": "3"
          }
        }
      }
    },
    {
      "id": "7",
      "type": "members",
      "links": {
        "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/7"
      },
      "attributes": {
        "last_read_at_unix": 0,
        "unread_message_count": 0,
        "is_room_visible": false,
        "user_typing": null
      },
      "relationships": {
        "room": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/7/relationships/room",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/7/room"
          },
          "data": {
            "type": "rooms",
            "id": "6"
          }
        },
        "user": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/7/relationships/user",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/7/user"
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
    "record_count": 6
  },
  "links": {
    "first": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members?page%5Bnumber%5D=1&page%5Bsize%5D=25",
    "last": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members?page%5Bnumber%5D=1&page%5Bsize%5D=25"
  }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members" %}
{% api-method-summary %}
create member
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
    "id": "8",
    "type": "members",
    "links": {
      "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/8"
    },
    "attributes": {
      "last_read_at_unix": 0,
      "unread_message_count": 2,
      "is_room_visible": true,
      "user_typing": null
    },
    "relationships": {
      "room": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/8/relationships/room",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/8/room"
        },
        "data": {
          "type": "rooms",
          "id": "1"
        }
      },
      "user": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/8/relationships/user",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/8/user"
        },
        "data": {
          "type": "users",
          "id": "3"
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

{% api-method method="put" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/{:id}" %}
{% api-method-summary %}
update members
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
    "type": "members",
    "links": {
      "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/1"
    },
    "attributes": {
      "last_read_at_unix": 1542602860,
      "unread_message_count": 1,
      "is_room_visible": true,
      "user_typing": null
    },
    "relationships": {
      "room": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/1/relationships/room",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/1/room"
        },
        "data": {
          "type": "rooms",
          "id": "1"
        }
      },
      "user": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/1/relationships/user",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/1/user"
        },
        "data": {
          "type": "users",
          "id": "2"
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

{% api-method method="delete" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/members/{:id}" %}
{% api-method-summary %}
delete member
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
