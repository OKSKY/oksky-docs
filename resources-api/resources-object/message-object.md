# Message object

## Fields

| Field | Type | Description | Editable |
| :--- | :--- | :--- | :--- |
| content | string |  |  |
| kind | string |  |  |
| settings | object |  |  |
| status | integer |  |  |
| info | object |  |  |
| tags | array |  |  |
| created\_at | datetime |  |  |
| deleted\_at | datetime |  |  |
| updated\_at | datetime |  |  |
| created\_at\_unix | integer |  |  |
| deleted\_at\_unix | integer |  |  |

## Filters

| Field | Description |
| :--- | :--- |
| id | ID |
| kind | 次の項目から選択 \[text, link, image, video, audio, location, sticker, action\_link, maltiple, rich\_content, stamp, contact, form, item, file\] |
| room\_id | RoomのID |
| after\_created\_at | 指定時刻より後に作成されたメッセージ。IntegerのUNIX時間を設定 |
| room\_kind | 次の項目から選択 \[direct\_room, group\_room, support\_room\] |
| before\_created\_at | 指定時刻より前に作成されたメッセージ。IntegerのUNIX時間を設定 |
| query |  |
| start\_date | 指定時刻の日付以降に作成されたメッセージ。IntegerのUNIX時間を設定 |
| end\_date | 指定時刻の日付以前に作成されたメッセージ。IntegerのUNIX時間を設定 |

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/23ad71d472b2b38669f3)

{% api-method method="get" host="" path="https://{YOUR\_OKSKY\_DOMAIN}/rapi/v1/messages/{:id}" %}
{% api-method-summary %}
find message
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
    "type": "messages",
    "links": {
      "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/messages/1"
    },
    "attributes": {
      "content": "first message",
      "kind": "text",
      "settings": {},
      "status": "posted",
      "info": {},
      "tags": [],
      "created_at": "2018-11-19T13:47:40.865+09:00",
      "deleted_at": null,
      "updated_at": "2018-11-19T13:47:40.865+09:00",
      "created_at_unix": 1542602860,
      "deleted_at_unix": null
    },
    "relationships": {
      "room": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/messages/1/relationships/room",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/messages/1/room"
        },
        "data": {
          "type": "rooms",
          "id": "1"
        }
      },
      "user": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/messages/1/relationships/user",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/messages/1/user"
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

{% api-method method="get" host="" path="https://{YOUR\_OKSKY\_DOMAIN}/rapi/v1/messages" %}
{% api-method-summary %}
search messages
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
      "type": "messages",
      "links": {
        "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/messages/1"
      },
      "attributes": {
        "content": "first message",
        "kind": "text",
        "settings": {},
        "status": "posted",
        "info": {},
        "tags": [],
        "created_at": "2018-11-19T13:47:40.865+09:00",
        "deleted_at": null,
        "updated_at": "2018-11-19T13:47:40.865+09:00",
        "created_at_unix": 1542602860,
        "deleted_at_unix": null
      },
      "relationships": {
        "room": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/messages/1/relationships/room",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/messages/1/room"
          },
          "data": {
            "type": "rooms",
            "id": "1"
          }
        },
        "user": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/messages/1/relationships/user",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/messages/1/user"
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
      "type": "messages",
      "links": {
        "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/messages/2"
      },
      "attributes": {
        "content": "Message Content",
        "kind": "text",
        "settings": {},
        "status": "posted",
        "info": {},
        "tags": [],
        "created_at": "2018-11-19T14:01:17.850+09:00",
        "deleted_at": null,
        "updated_at": "2018-11-19T14:35:31.354+09:00",
        "created_at_unix": 1542603677,
        "deleted_at_unix": null
      },
      "relationships": {
        "room": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/messages/2/relationships/room",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/messages/2/room"
          },
          "data": {
            "type": "rooms",
            "id": "1"
          }
        },
        "user": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/messages/2/relationships/user",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/messages/2/user"
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
    "record_count": 2
  },
  "links": {
    "first": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/messages?page%5Bnumber%5D=1&page%5Bsize%5D=25",
    "last": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/messages?page%5Bnumber%5D=1&page%5Bsize%5D=25"
  }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="" path="https://{YOUR\_OKSKY\_DOMAIN}/rapi/v1/messages" %}
{% api-method-summary %}
create message
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
    "id": "3",
    "type": "messages",
    "links": {
      "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/messages/3"
    },
    "attributes": {
      "content": "textt",
      "kind": "text",
      "settings": {},
      "status": "posted",
      "info": {},
      "tags": [],
      "created_at": "2018-11-20T10:06:25.393+09:00",
      "deleted_at": null,
      "updated_at": "2018-11-20T10:06:25.393+09:00",
      "created_at_unix": 1542675985,
      "deleted_at_unix": null
    },
    "relationships": {
      "room": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/messages/3/relationships/room",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/messages/3/room"
        },
        "data": {
          "type": "rooms",
          "id": "1"
        }
      },
      "user": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/messages/3/relationships/user",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/messages/3/user"
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

{% api-method method="put" host="" path="https://{YOUR\_OKSKY\_DOMAIN}/rapi/v1/messages/{:id}" %}
{% api-method-summary %}
update messages
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
    "type": "messages",
    "links": {
      "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/messages/1"
    },
    "attributes": {
      "content": "first message",
      "kind": "text",
      "settings": {},
      "status": "posted",
      "info": {},
      "tags": [],
      "created_at": "2018-11-19T13:47:40.865+09:00",
      "deleted_at": null,
      "updated_at": "2018-11-19T13:47:40.865+09:00",
      "created_at_unix": 1542602860,
      "deleted_at_unix": null
    },
    "relationships": {
      "room": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/messages/1/relationships/room",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/messages/1/room"
        },
        "data": {
          "type": "rooms",
          "id": "1"
        }
      },
      "user": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/messages/1/relationships/user",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/messages/1/user"
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

{% api-method method="delete" host="" path="https://{YOUR\_OKSKY\_DOMAIN}/rapi/v1/messages/{:id}" %}
{% api-method-summary %}
delete message
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

{% api-method method="get" host="" path="https://{YOUR\_OKSKY\_DOMAIN}/rapi/v1/messages/search" %}
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

```text

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="" path="https://{YOUR\_OKSKY\_DOMAIN}/rapi/v1/messages/export" %}
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

```text
id,content,room_name,room_id,created_at,posted_at,user_id,user_name,kind,src_url,tags_all
1,a,kiwi-barren-cabbage-1-wbbRxtFEf9E,3,2018/11/08 17:53,2018/11/08 17:53,2,1811081753033735,text,"",""
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

