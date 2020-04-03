# Room object

## Fields

| Field | Type | Description | Editable |
| :--- | :--- | :--- | :--- |
| name | string |  |  |
| description | string |  |  |
| is\_private | boolean |  |  |
| settings | object |  |  |
| kind | string | support\_room =&gt; 1 来訪者 : 複数の接客者のグループチャット、direct\_room =&gt; 2 接客者のみチャットルーム、 group\_room =&gt; 複数名の接客者が含まれるチャットルーム |  |
| enabled | boolean |  |  |
| room\_code | string | ルームコード |  |
| awaiting\_support | boolean | 接客待ちか否か |  |
| created\_at\_unix | integer | 作成日時のUnixtime |  |
| created\_at | datetime | 作成日時 |  |
| is\_external | boolean | サードパーティメッセージングサービスとの連携が行われているか否か |  |

## Filters

| Field | Description |
| :--- | :--- |
| id | ID |
| name | Roomの名前 |
| is\_private | Booleanまたは1,0で指定 |
| kind | 次の項目から選択 \[direct\_room, group\_room, support\_room\] |
| awaiting\_support | Booleanまたは1,0で指定 |
| replied |  |
| starred |  |
| private\_rooms |  |
| private\_rooms\_with\_active\_support |  |
| private\_rooms\_with\_active\_or\_awaiting\_support |  |
| current\_user\_is\_member |  |
| support\_rooms\_with\_active\_support |  |
| support\_rooms\_with\_active\_or\_awaiting\_support |  |
| current\_users\_support\_rooms\_with\_active\_or\_awaiting\_support |  |
| name\_like | Room名の部分一致 |
| support\_room\_name\_like |  |
| sort\_unread\_read\_for\_user\_id |  |

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/e59c43089a9d822572e4)

{% api-method method="get" host="" path="https://{YOUR\_OKSKY\_DOMAIN}/rapi/v1/rooms/{:id}" %}
{% api-method-summary %}
find room
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
    "type": "rooms",
    "links": {
      "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1"
    },
    "attributes": {
      "name": "mint-hamstrung-show-1-GfWWnb8pNgo",
      "description": "",
      "is_private": false,
      "settings": {
        "message_classify": true,
        "message_dialog": false
      },
      "kind": "support_room",
      "enabled": null,
      "room_code": null,
      "awaiting_support": true,
      "created_at_unix": 1542602860,
      "created_at": "2018-11-19T13:47:40.535+09:00",
      "is_external": false
    },
    "relationships": {
      "messages": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/relationships/messages",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/messages"
        },
        "data": [
          {
            "type": "messages",
            "id": "1"
          }
        ]
      },
      "members": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/relationships/members",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/members"
        },
        "data": [
          {
            "type": "members",
            "id": "1"
          }
        ]
      },
      "users": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/relationships/users",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/users"
        },
        "data": [
          {
            "type": "users",
            "id": "2"
          }
        ]
      },
      "create_user": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/relationships/create_user",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/create_user"
        },
        "data": {
          "type": "users",
          "id": "2"
        }
      },
      "latest_message": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/relationships/latest_message",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/latest_message"
        },
        "data": {
          "type": "messages",
          "id": "1"
        }
      },
      "latest_memo": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/relationships/latest_memo",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/latest_memo"
        },
        "data": null
      },
      "client": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/relationships/client",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/client"
        },
        "data": {
          "type": "clients",
          "id": "1"
        }
      },
      "helped_room": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/relationships/helped_room",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/helped_room"
        },
        "data": null
      },
      "supports": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/relationships/supports",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/supports"
        },
        "data": []
      },
      "support_draft_messages": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/relationships/support_draft_messages",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/support_draft_messages"
        },
        "data": []
      },
      "suggestion": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/relationships/suggestion",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/suggestion"
        }
      },
      "memos": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/relationships/memos",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/memos"
        },
        "data": []
      }
    }
  }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="" path="https://{YOUR\_OKSKY\_DOMAIN}/rapi/v1/rooms" %}
{% api-method-summary %}
search rooms
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
      "type": "rooms",
      "links": {
        "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1"
      },
      "attributes": {
        "name": "mint-hamstrung-show-1-GfWWnb8pNgo",
        "description": "",
        "is_private": false,
        "settings": {
          "message_classify": true,
          "message_dialog": false
        },
        "kind": "support_room",
        "enabled": null,
        "room_code": null,
        "awaiting_support": true,
        "created_at_unix": 1542602860,
        "created_at": "2018-11-19T13:47:40.535+09:00",
        "is_external": false
      },
      "relationships": {
        "messages": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/relationships/messages",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/messages"
          },
          "data": [
            {
              "type": "messages",
              "id": "1"
            }
          ]
        },
        "members": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/relationships/members",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/members"
          },
          "data": [
            {
              "type": "members",
              "id": "1"
            }
          ]
        },
        "users": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/relationships/users",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/users"
          },
          "data": [
            {
              "type": "users",
              "id": "2"
            }
          ]
        },
        "create_user": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/relationships/create_user",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/create_user"
          },
          "data": {
            "type": "users",
            "id": "2"
          }
        },
        "latest_message": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/relationships/latest_message",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/latest_message"
          },
          "data": {
            "type": "messages",
            "id": "1"
          }
        },
        "latest_memo": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/relationships/latest_memo",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/latest_memo"
          },
          "data": null
        },
        "client": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/relationships/client",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/client"
          },
          "data": {
            "type": "clients",
            "id": "1"
          }
        },
        "helped_room": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/relationships/helped_room",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/helped_room"
          },
          "data": null
        },
        "supports": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/relationships/supports",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/supports"
          },
          "data": []
        },
        "support_draft_messages": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/relationships/support_draft_messages",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/support_draft_messages"
          },
          "data": []
        },
        "suggestion": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/relationships/suggestion",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/suggestion"
          }
        },
        "memos": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/relationships/memos",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/memos"
          },
          "data": []
        }
      }
    }
  ],
  "meta": {
    "record_count": 1
  },
  "links": {
    "first": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms?page%5Bnumber%5D=1&page%5Bsize%5D=25",
    "last": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms?page%5Bnumber%5D=1&page%5Bsize%5D=25"
  }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="" path="https://{YOUR\_OKSKY\_DOMAIN}/rapi/v1/rooms" %}
{% api-method-summary %}
create room
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
    "id": "2",
    "type": "rooms",
    "links": {
      "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/2"
    },
    "attributes": {
      "name": "navy-intelligent-quiet20181119",
      "description": "",
      "is_private": false,
      "settings": {},
      "kind": "support_room",
      "enabled": null,
      "room_code": null,
      "awaiting_support": false,
      "created_at_unix": 1542603242,
      "created_at": "2018-11-19T13:54:02.730+09:00",
      "is_external": false
    },
    "relationships": {
      "messages": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/2/relationships/messages",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/2/messages"
        },
        "data": []
      },
      "members": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/2/relationships/members",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/2/members"
        },
        "data": []
      },
      "users": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/2/relationships/users",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/2/users"
        },
        "data": []
      },
      "create_user": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/2/relationships/create_user",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/2/create_user"
        },
        "data": {
          "type": "users",
          "id": "1"
        }
      },
      "latest_message": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/2/relationships/latest_message",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/2/latest_message"
        },
        "data": null
      },
      "latest_memo": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/2/relationships/latest_memo",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/2/latest_memo"
        },
        "data": null
      },
      "client": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/2/relationships/client",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/2/client"
        },
        "data": {
          "type": "clients",
          "id": "1"
        }
      },
      "helped_room": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/2/relationships/helped_room",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/2/helped_room"
        },
        "data": null
      },
      "supports": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/2/relationships/supports",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/2/supports"
        },
        "data": []
      },
      "support_draft_messages": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/2/relationships/support_draft_messages",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/2/support_draft_messages"
        },
        "data": []
      },
      "suggestion": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/2/relationships/suggestion",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/2/suggestion"
        }
      },
      "memos": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/2/relationships/memos",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/2/memos"
        },
        "data": []
      }
    }
  }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="put" host="" path="https://{YOUR\_OKSKY\_DOMAIN}/rapi/v1/rooms/{:id}" %}
{% api-method-summary %}
update rooms
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
    "type": "rooms",
    "links": {
      "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1"
    },
    "attributes": {
      "name": "mint-hamstrung-show-1-GfWWnb8pNgo",
      "description": "",
      "is_private": false,
      "settings": {
        "message_classify": true,
        "message_dialog": false
      },
      "kind": "support_room",
      "enabled": null,
      "room_code": null,
      "awaiting_support": false,
      "created_at_unix": 1542602860,
      "created_at": "2018-11-19T13:47:40.535+09:00",
      "is_external": false
    },
    "relationships": {
      "messages": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/relationships/messages",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/messages"
        },
        "data": [
          {
            "type": "messages",
            "id": "1"
          },
          {
            "type": "messages",
            "id": "5"
          },
          {
            "type": "messages",
            "id": "2"
          }
        ]
      },
      "members": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/relationships/members",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/members"
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
      },
      "users": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/relationships/users",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/users"
        },
        "data": [
          {
            "type": "users",
            "id": "1"
          },
          {
            "type": "users",
            "id": "2"
          },
          {
            "type": "users",
            "id": "3"
          }
        ]
      },
      "create_user": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/relationships/create_user",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/create_user"
        },
        "data": {
          "type": "users",
          "id": "2"
        }
      },
      "latest_message": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/relationships/latest_message",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/latest_message"
        },
        "data": {
          "type": "messages",
          "id": "2"
        }
      },
      "latest_memo": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/relationships/latest_memo",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/latest_memo"
        },
        "data": {
          "type": "memos",
          "id": "2"
        }
      },
      "client": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/relationships/client",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/client"
        },
        "data": {
          "type": "clients",
          "id": "1"
        }
      },
      "helped_room": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/relationships/helped_room",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/helped_room"
        },
        "data": null
      },
      "supports": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/relationships/supports",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/supports"
        },
        "data": [
          {
            "type": "supports",
            "id": "2"
          },
          {
            "type": "supports",
            "id": "3"
          },
          {
            "type": "supports",
            "id": "4"
          }
        ]
      },
      "support_draft_messages": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/relationships/support_draft_messages",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/support_draft_messages"
        },
        "data": [
          {
            "type": "support_draft_messages",
            "id": "4"
          },
          {
            "type": "support_draft_messages",
            "id": "2"
          }
        ]
      },
      "suggestion": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/relationships/suggestion",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/suggestion"
        }
      },
      "memos": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/relationships/memos",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/1/memos"
        },
        "data": [
          {
            "type": "memos",
            "id": "2"
          },
          {
            "type": "memos",
            "id": "1"
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

{% api-method method="delete" host="" path="https://{YOUR\_OKSKY\_DOMAIN}/rapi/v1/rooms/{:id}" %}
{% api-method-summary %}
delete room
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

{% api-method method="get" host="" path="https://{YOUR\_OKSKY\_DOMAIN}/rapi/v1/rooms/{:id}/history" %}
{% api-method-summary %}
history
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
1,a,onyx-corny-spoon-1-eEcWoIfzYnU,17,2018/11/08 11:46,2018/11/08 11:46,12,1811071416537033,text,"",""
2,b,onyx-corny-spoon-1-eEcWoIfzYnU,17,2018/11/08 11:46,2018/11/08 11:46,12,1811071416537033,text,"",""
3,c,onyx-corny-spoon-1-eEcWoIfzYnU,17,2018/11/08 11:46,2018/11/08 11:46,12,1811071416537033,text,"",""
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="put" host="" path="https://{YOUR\_OKSKY\_DOMAIN}/rapi/v1/rooms/{:id}/approve\_support\_draft\_messages" %}
{% api-method-summary %}
approve support draft messages
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
      "type": "support_draft_messages",
      "links": {
        "self": "/rapi/v1/support_draft_messages/2"
      },
      "attributes": {
        "message_content": "Message Content",
        "kind": "text",
        "settings": {},
        "status": "approved",
        "resolved_time_unix": 1542605731,
        "comment": null,
        "create_user_resolved_read_time_unix": null,
        "created_at_unix": 1542603677,
        "updated_at_unix": 1542605731
      },
      "relationships": {
        "support": {
          "links": {
            "self": "/rapi/v1/support_draft_messages/2/relationships/support",
            "related": "/rapi/v1/support_draft_messages/2/support"
          },
          "data": {
            "type": "supports",
            "id": "2"
          }
        },
        "resolved_user": {
          "links": {
            "self": "/rapi/v1/support_draft_messages/2/relationships/resolved_user",
            "related": "/rapi/v1/support_draft_messages/2/resolved_user"
          },
          "data": {
            "type": "users",
            "id": "1"
          }
        },
        "created_user": {
          "links": {
            "self": "/rapi/v1/support_draft_messages/2/relationships/created_user",
            "related": "/rapi/v1/support_draft_messages/2/created_user"
          },
          "data": {
            "type": "users",
            "id": "1"
          }
        },
        "room": {
          "links": {
            "self": "/rapi/v1/support_draft_messages/2/relationships/room",
            "related": "/rapi/v1/support_draft_messages/2/room"
          },
          "data": {
            "type": "rooms",
            "id": "1"
          }
        }
      }
    }
  ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="put" host="" path="https://{YOUR\_OKSKY\_DOMAIN}/rapi/v1/rooms/{:id}/reject\_support\_draft\_messages" %}
{% api-method-summary %}
reject support draft messages
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
      "type": "support_draft_messages",
      "links": {
        "self": "/rapi/v1/support_draft_messages/2"
      },
      "attributes": {
        "message_content": "Message Content",
        "kind": "text",
        "settings": {},
        "status": "rejected",
        "resolved_time_unix": 1542606103,
        "comment": null,
        "create_user_resolved_read_time_unix": null,
        "created_at_unix": 1542603677,
        "updated_at_unix": 1542606103
      },
      "relationships": {
        "support": {
          "links": {
            "self": "/rapi/v1/support_draft_messages/2/relationships/support",
            "related": "/rapi/v1/support_draft_messages/2/support"
          },
          "data": {
            "type": "supports",
            "id": "2"
          }
        },
        "resolved_user": {
          "links": {
            "self": "/rapi/v1/support_draft_messages/2/relationships/resolved_user",
            "related": "/rapi/v1/support_draft_messages/2/resolved_user"
          },
          "data": {
            "type": "users",
            "id": "1"
          }
        },
        "created_user": {
          "links": {
            "self": "/rapi/v1/support_draft_messages/2/relationships/created_user",
            "related": "/rapi/v1/support_draft_messages/2/created_user"
          },
          "data": {
            "type": "users",
            "id": "1"
          }
        },
        "room": {
          "links": {
            "self": "/rapi/v1/support_draft_messages/2/relationships/room",
            "related": "/rapi/v1/support_draft_messages/2/room"
          },
          "data": {
            "type": "rooms",
            "id": "1"
          }
        }
      }
    }
  ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="" path="https://{YOUR\_OKSKY\_DOMAIN}/rapi/v1/rooms/create\_or\_find\_group\_room" %}
{% api-method-summary %}
create or find group room
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
    "id": "3",
    "type": "rooms",
    "links": {
      "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/3"
    },
    "attributes": {
      "name": "lavendar-bald-notebook20181119",
      "description": "",
      "is_private": false,
      "settings": {},
      "kind": "group_room",
      "enabled": null,
      "room_code": null,
      "awaiting_support": false,
      "created_at_unix": 1542606135,
      "created_at": "2018-11-19T14:42:15.079+09:00",
      "is_external": false
    },
    "relationships": {
      "messages": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/3/relationships/messages",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/3/messages"
        },
        "data": []
      },
      "members": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/3/relationships/members",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/3/members"
        },
        "data": [
          {
            "type": "members",
            "id": "2"
          }
        ]
      },
      "users": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/3/relationships/users",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/3/users"
        },
        "data": [
          {
            "type": "users",
            "id": "1"
          }
        ]
      },
      "create_user": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/3/relationships/create_user",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/3/create_user"
        },
        "data": {
          "type": "users",
          "id": "1"
        }
      },
      "latest_message": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/3/relationships/latest_message",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/3/latest_message"
        },
        "data": null
      },
      "latest_memo": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/3/relationships/latest_memo",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/3/latest_memo"
        },
        "data": null
      },
      "client": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/3/relationships/client",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/3/client"
        },
        "data": {
          "type": "clients",
          "id": "1"
        }
      },
      "helped_room": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/3/relationships/helped_room",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/3/helped_room"
        },
        "data": {
          "type": "rooms",
          "id": "1"
        }
      },
      "supports": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/3/relationships/supports",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/3/supports"
        },
        "data": []
      },
      "support_draft_messages": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/3/relationships/support_draft_messages",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/3/support_draft_messages"
        },
        "data": []
      },
      "suggestion": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/3/relationships/suggestion",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/3/suggestion"
        }
      },
      "memos": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/3/relationships/memos",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/3/memos"
        },
        "data": []
      }
    }
  }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="" path="https://{YOUR\_OKSKY\_DOMAIN}/rapi/v1/rooms/create\_or\_find\_direct\_room" %}
{% api-method-summary %}
create or find direct room
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
    "id": "5",
    "type": "rooms",
    "links": {
      "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/5"
    },
    "attributes": {
      "name": "spinach-lavish-owl20181119",
      "description": "",
      "is_private": true,
      "settings": {},
      "kind": "direct_room",
      "enabled": null,
      "room_code": null,
      "awaiting_support": false,
      "created_at_unix": 1542606247,
      "created_at": "2018-11-19T14:44:07.138+09:00",
      "is_external": false
    },
    "relationships": {
      "messages": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/5/relationships/messages",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/5/messages"
        },
        "data": []
      },
      "members": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/5/relationships/members",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/5/members"
        },
        "data": [
          {
            "type": "members",
            "id": "5"
          }
        ]
      },
      "users": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/5/relationships/users",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/5/users"
        },
        "data": [
          {
            "type": "users",
            "id": "1"
          }
        ]
      },
      "create_user": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/5/relationships/create_user",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/5/create_user"
        },
        "data": {
          "type": "users",
          "id": "1"
        }
      },
      "latest_message": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/5/relationships/latest_message",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/5/latest_message"
        },
        "data": null
      },
      "latest_memo": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/5/relationships/latest_memo",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/5/latest_memo"
        },
        "data": null
      },
      "client": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/5/relationships/client",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/5/client"
        },
        "data": {
          "type": "clients",
          "id": "1"
        }
      },
      "helped_room": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/5/relationships/helped_room",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/5/helped_room"
        },
        "data": null
      },
      "supports": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/5/relationships/supports",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/5/supports"
        },
        "data": []
      },
      "support_draft_messages": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/5/relationships/support_draft_messages",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/5/support_draft_messages"
        },
        "data": []
      },
      "suggestion": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/5/relationships/suggestion",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/5/suggestion"
        }
      },
      "memos": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/5/relationships/memos",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/rooms/5/memos"
        },
        "data": []
      }
    }
  }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="" path="https://{YOUR\_OKSKY\_DOMAIN}/rapi/v1/rooms/room\_counts" %}
{% api-method-summary %}
room counts
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
    "type": "room_counts",
    "id": "1",
    "attributes": {
      "total_replied_count": 1,
      "replied_count_by_supporter": {
        "1": 1
      },
      "total_unreplied_count": 0,
      "unreplied_count_by_supporter": {},
      "supporting_rooms_count": 1,
      "awaiting_support_count": 1,
      "unread_supports_messages_by_user_count": {
        "1": 1
      },
      "unread_private_messages_by_user_count": {},
      "private_rooms_by_user_count": {},
      "support_draft_messages_in_review_by_user_count": {},
      "total_support_draft_messages_in_review": 0,
      "unread_support_draft_messages_approved_by_user_count": {},
      "unread_support_draft_messages_rejected_by_user_count": {
        "1": 1
      }
    }
  }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

