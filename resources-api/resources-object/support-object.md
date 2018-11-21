# Support object

## Fields

| Field | Type | Description | Editable |
| :--- | :--- | :--- | :--- |
| end_time_unix | integer |  |  |
| start_time_unix | integer |  |  |

## Filters

| Field | Description |
| :--- | :--- |
| id | ID |
| active_or_end_time_gt | `end_time` が指定時刻以降、または空のサポート。IntegerのUNIX時間を設定 |
| to | `start_time` が指定時刻の日付以前、または `end_time` が空のサポート。IntegerのUNIX時間を設定 |
| from | `end_time` が指定時刻の日付以降、または空のサポート。IntegerのUNIX時間を設定 |
| room_or_operator | Roomの名前、部屋に関連するUserの `email`, `name`, `full_name` のいずれかに部分一致 |
| active | 1: `end_time` が空のサポート。 2: `end_time` が空ではないサポート。 |
| status | `active`: `end_time` が空のサポート。 `ended`: `end_time` が空ではないサポート。 |
| user_id | UserのID |
| room_id | RoomのID |
| replied | `end_time` が空で、関連するRoomに接客者が返信しているか。 1: 返信済 0: 未返信 |

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/b7c22f61358e725d294b)

{% api-method method="get" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/{:id}" %}
{% api-method-summary %}
find support
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
    "id": "2",
    "type": "supports",
    "links": {
      "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/2"
    },
    "attributes": {
      "end_time_unix": null,
      "start_time_unix": 1542603555
    },
    "relationships": {
      "room": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/2/relationships/room",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/2/room"
        },
        "data": {
          "type": "rooms",
          "id": "1"
        }
      },
      "user": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/2/relationships/user",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/2/user"
        },
        "data": {
          "type": "users",
          "id": "1"
        }
      },
      "latest_message": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/2/relationships/latest_message",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/2/latest_message"
        },
        "data": {
          "type": "messages",
          "id": "2"
        }
      },
      "customer": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/2/relationships/customer",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/2/customer"
        },
        "data": {
          "type": "users",
          "id": "2"
        }
      },
      "members": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/2/relationships/members",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/2/members"
        },
        "data": [
          {
            "type": "members",
            "id": "1"
          },
          {
            "type": "members",
            "id": "3"
          },
          {
            "type": "members",
            "id": "8"
          }
        ]
      }
    }
  }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports" %}
{% api-method-summary %}
search supports
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
      "id": "2",
      "type": "supports",
      "links": {
        "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/2"
      },
      "attributes": {
        "end_time_unix": null,
        "start_time_unix": 1542603555
      },
      "relationships": {
        "room": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/2/relationships/room",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/2/room"
          },
          "data": {
            "type": "rooms",
            "id": "1"
          }
        },
        "user": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/2/relationships/user",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/2/user"
          },
          "data": {
            "type": "users",
            "id": "1"
          }
        },
        "latest_message": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/2/relationships/latest_message",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/2/latest_message"
          },
          "data": {
            "type": "messages",
            "id": "2"
          }
        },
        "customer": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/2/relationships/customer",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/2/customer"
          },
          "data": {
            "type": "users",
            "id": "2"
          }
        },
        "members": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/2/relationships/members",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/2/members"
          },
          "data": [
            {
              "type": "members",
              "id": "1"
            },
            {
              "type": "members",
              "id": "3"
            },
            {
              "type": "members",
              "id": "8"
            }
          ]
        }
      }
    }
  ],
  "meta": {
    "record_count": 1
  },
  "links": {
    "first": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports?page%5Bnumber%5D=1&page%5Bsize%5D=25",
    "last": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports?page%5Bnumber%5D=1&page%5Bsize%5D=25"
  }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/search" %}
{% api-method-summary %}
search
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

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}


{% api-method method="get" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/export" %}
{% api-method-summary %}
export
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
id,room_id,room_name,start_time,end_time,user_id,user_name
1,3,kiwi-barren-cabbage-1-wbbRxtFEf9E,2018/11/08 17:53,,1,Manager
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="put" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/end_support" %}
{% api-method-summary %}
end support
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
  "data": {
    "id": "2",
    "type": "supports",
    "links": {
      "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/2"
    },
    "attributes": {
      "end_time_unix": 1542679562,
      "start_time_unix": 1542603555
    },
    "relationships": {
      "room": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/2/relationships/room",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/2/room"
        },
        "data": {
          "type": "rooms",
          "id": "1"
        }
      },
      "user": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/2/relationships/user",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/2/user"
        },
        "data": {
          "type": "users",
          "id": "1"
        }
      },
      "latest_message": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/2/relationships/latest_message",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/2/latest_message"
        },
        "data": {
          "type": "messages",
          "id": "2"
        }
      },
      "customer": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/2/relationships/customer",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/2/customer"
        },
        "data": {
          "type": "users",
          "id": "2"
        }
      },
      "members": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/2/relationships/members",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/2/members"
        },
        "data": [
          {
            "type": "members",
            "id": "1"
          },
          {
            "type": "members",
            "id": "3"
          },
          {
            "type": "members",
            "id": "8"
          }
        ]
      }
    }
  }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="put" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/reassign" %}
{% api-method-summary %}
reassign
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
      "id": "3",
      "type": "supports",
      "links": {
        "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/3"
      },
      "attributes": {
        "end_time_unix": null,
        "start_time_unix": 1542679579
      },
      "relationships": {
        "room": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/3/relationships/room",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/3/room"
          },
          "data": {
            "type": "rooms",
            "id": "1"
          }
        },
        "user": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/3/relationships/user",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/3/user"
          },
          "data": {
            "type": "users",
            "id": "1"
          }
        },
        "latest_message": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/3/relationships/latest_message",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/3/latest_message"
          },
          "data": {
            "type": "messages",
            "id": "2"
          }
        },
        "customer": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/3/relationships/customer",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/3/customer"
          },
          "data": {
            "type": "users",
            "id": "2"
          }
        },
        "members": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/3/relationships/members",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/3/members"
          },
          "data": [
            {
              "type": "members",
              "id": "1"
            },
            {
              "type": "members",
              "id": "3"
            },
            {
              "type": "members",
              "id": "8"
            }
          ]
        }
      }
    },
    {
      "id": "2",
      "type": "supports",
      "links": {
        "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/2"
      },
      "attributes": {
        "end_time_unix": 1542679562,
        "start_time_unix": 1542603555
      },
      "relationships": {
        "room": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/2/relationships/room",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/2/room"
          },
          "data": {
            "type": "rooms",
            "id": "1"
          }
        },
        "user": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/2/relationships/user",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/2/user"
          },
          "data": {
            "type": "users",
            "id": "1"
          }
        },
        "latest_message": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/2/relationships/latest_message",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/2/latest_message"
          },
          "data": {
            "type": "messages",
            "id": "2"
          }
        },
        "customer": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/2/relationships/customer",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/2/customer"
          },
          "data": {
            "type": "users",
            "id": "2"
          }
        },
        "members": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/2/relationships/members",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/2/members"
          },
          "data": [
            {
              "type": "members",
              "id": "1"
            },
            {
              "type": "members",
              "id": "3"
            },
            {
              "type": "members",
              "id": "8"
            }
          ]
        }
      }
    }
  ],
  "meta": {
    "record_count": 2
  },
  "links": {
    "first": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports?page%5Bnumber%5D=1&page%5Bsize%5D=25",
    "last": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports?page%5Bnumber%5D=1&page%5Bsize%5D=25"
  }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="put" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/reopen" %}
{% api-method-summary %}
reopen
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
  "data": {
    "id": "4",
    "type": "supports",
    "links": {
      "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/4"
    },
    "attributes": {
      "end_time_unix": null,
      "start_time_unix": 1542679622
    },
    "relationships": {
      "room": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/4/relationships/room",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/4/room"
        },
        "data": {
          "type": "rooms",
          "id": "1"
        }
      },
      "user": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/4/relationships/user",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/4/user"
        },
        "data": {
          "type": "users",
          "id": "1"
        }
      },
      "latest_message": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/4/relationships/latest_message",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/4/latest_message"
        },
        "data": {
          "type": "messages",
          "id": "2"
        }
      },
      "customer": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/4/relationships/customer",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/4/customer"
        },
        "data": {
          "type": "users",
          "id": "2"
        }
      },
      "members": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/4/relationships/members",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/supports/4/members"
        },
        "data": [
          {
            "type": "members",
            "id": "1"
          },
          {
            "type": "members",
            "id": "3"
          },
          {
            "type": "members",
            "id": "8"
          }
        ]
      }
    }
  }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}
