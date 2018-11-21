# SupportDraftMessage object

## Fields

| Field | Type | Description | Editable |
| :--- | :--- | :--- | :--- |
| message_content | string |  |  |
| kind | string |  |  |
| settings | object |  |  |
| status | string |  |  |
| resolved_time_unix | integer |  |  |
| comment | string |  |  |
| create_user_resolved_read_time_unix | integer |  |  |
| created_at_unix | integer |  |  |
| updated_at_unix | integer |  |  |

## Filters

| Field | Description |
| :--- | :--- |
| id | ID |
| resolved_user_id |  |
| created_user_id |  |
| approved | 1: `status` が `approved` で絞り込み |
| rejected | 1: `status` が `rejected` で絞り込み |
| resolved | 1: `resolved_user_id` と `resolved_time` が空でない条件で絞り込み |
| in_review | 1: `status` が `in_review` または空、且つ、`resolved_user_id` と `resolved_time` が空で無い条件で絞り込み |
| read | 1: `create_user_resolved_read_time` が空でない条件で絞り込み 0: `create_user_resolved_read_time` が空の条件で絞り込み |
| content_or_room_name_like | `message_content` または関連するRoomの名前に部分一致 |
| from_created_at | 指定時刻の日付以降に作成されたデータ。IntegerのUNIX時間を設定 |
| to_created_at | 指定時刻の日付以前に作成されたデータ。IntegerのUNIX時間を設定 |

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/39359c5335f2548543e9)

{% api-method method="get" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages/{:id}" %}
{% api-method-summary %}
find support draft message
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
    "type": "support_draft_messages",
    "links": {
      "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages/2"
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
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages/2/relationships/support",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages/2/support"
        },
        "data": {
          "type": "supports",
          "id": "2"
        }
      },
      "resolved_user": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages/2/relationships/resolved_user",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages/2/resolved_user"
        },
        "data": {
          "type": "users",
          "id": "1"
        }
      },
      "created_user": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages/2/relationships/created_user",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages/2/created_user"
        },
        "data": {
          "type": "users",
          "id": "1"
        }
      },
      "room": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages/2/relationships/room",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages/2/room"
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

{% api-method method="get" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages" %}
{% api-method-summary %}
search support draft messages
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
        "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages/2"
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
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages/2/relationships/support",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages/2/support"
          },
          "data": {
            "type": "supports",
            "id": "2"
          }
        },
        "resolved_user": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages/2/relationships/resolved_user",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages/2/resolved_user"
          },
          "data": {
            "type": "users",
            "id": "1"
          }
        },
        "created_user": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages/2/relationships/created_user",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages/2/created_user"
          },
          "data": {
            "type": "users",
            "id": "1"
          }
        },
        "room": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages/2/relationships/room",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages/2/room"
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
    "first": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages?page%5Bnumber%5D=1&page%5Bsize%5D=25",
    "last": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages?page%5Bnumber%5D=1&page%5Bsize%5D=25"
  }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages" %}
{% api-method-summary %}
create support draft message
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
    "id": "4",
    "type": "support_draft_messages",
    "links": {
      "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages/4"
    },
    "attributes": {
      "message_content": null,
      "kind": "text",
      "settings": {},
      "status": "in_review",
      "resolved_time_unix": null,
      "comment": null,
      "create_user_resolved_read_time_unix": null,
      "created_at_unix": 1542681143,
      "updated_at_unix": 1542681143
    },
    "relationships": {
      "support": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages/4/relationships/support",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages/4/support"
        },
        "data": {
          "type": "supports",
          "id": "2"
        }
      },
      "resolved_user": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages/4/relationships/resolved_user",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages/4/resolved_user"
        },
        "data": null
      },
      "created_user": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages/4/relationships/created_user",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages/4/created_user"
        },
        "data": {
          "type": "users",
          "id": "1"
        }
      },
      "room": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages/4/relationships/room",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages/4/room"
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

{% api-method method="put" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages/{:id}" %}
{% api-method-summary %}
update support draft messages
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
    "id": "2",
    "type": "support_draft_messages",
    "links": {
      "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages/2"
    },
    "attributes": {
      "message_content": "Message Content",
      "kind": "text",
      "settings": {},
      "status": "in_review",
      "resolved_time_unix": null,
      "comment": "comment",
      "create_user_resolved_read_time_unix": null,
      "created_at_unix": 1542603677,
      "updated_at_unix": 1542681780
    },
    "relationships": {
      "support": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages/2/relationships/support",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages/2/support"
        },
        "data": {
          "type": "supports",
          "id": "2"
        }
      },
      "resolved_user": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages/2/relationships/resolved_user",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages/2/resolved_user"
        },
        "data": null
      },
      "created_user": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages/2/relationships/created_user",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages/2/created_user"
        },
        "data": {
          "type": "users",
          "id": "1"
        }
      },
      "room": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages/2/relationships/room",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages/2/room"
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

{% api-method method="delete" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages/{:id}" %}
{% api-method-summary %}
delete support draft message
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

{% api-method method="put" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages/mark_read_all_resolved" %}
{% api-method-summary %}
mark read all resolved
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
      "id": "4",
      "type": "support_draft_messages",
      "links": {
        "self": "/rapi/v1/support_draft_messages/4"
      },
      "attributes": {
        "message_content": null,
        "kind": "text",
        "settings": {},
        "status": "approved",
        "resolved_time_unix": null,
        "comment": null,
        "create_user_resolved_read_time_unix": 1542682190,
        "created_at_unix": 1542681143,
        "updated_at_unix": 1542682190
      },
      "relationships": {
        "support": {
          "links": {
            "self": "/rapi/v1/support_draft_messages/4/relationships/support",
            "related": "/rapi/v1/support_draft_messages/4/support"
          },
          "data": {
            "type": "supports",
            "id": "2"
          }
        },
        "resolved_user": {
          "links": {
            "self": "/rapi/v1/support_draft_messages/4/relationships/resolved_user",
            "related": "/rapi/v1/support_draft_messages/4/resolved_user"
          },
          "data": null
        },
        "created_user": {
          "links": {
            "self": "/rapi/v1/support_draft_messages/4/relationships/created_user",
            "related": "/rapi/v1/support_draft_messages/4/created_user"
          },
          "data": {
            "type": "users",
            "id": "1"
          }
        },
        "room": {
          "links": {
            "self": "/rapi/v1/support_draft_messages/4/relationships/room",
            "related": "/rapi/v1/support_draft_messages/4/room"
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

{% api-method method="put" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages/{:id}/approve" %}
{% api-method-summary %}
approve
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
    "type": "support_draft_messages",
    "links": {
      "self": "/rapi/v1/support_draft_messages/2"
    },
    "attributes": {
      "message_content": "Message Content",
      "kind": "text",
      "settings": {},
      "status": "approved",
      "resolved_time_unix": 1542682297,
      "comment": null,
      "create_user_resolved_read_time_unix": null,
      "created_at_unix": 1542603677,
      "updated_at_unix": 1542682297
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
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="put" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages/{:id}/reject" %}
{% api-method-summary %}
reject
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
    "type": "support_draft_messages",
    "links": {
      "self": "/rapi/v1/support_draft_messages/2"
    },
    "attributes": {
      "message_content": "Message Content",
      "kind": "text",
      "settings": {},
      "status": "approved",
      "resolved_time_unix": 1542682297,
      "comment": null,
      "create_user_resolved_read_time_unix": null,
      "created_at_unix": 1542603677,
      "updated_at_unix": 1542682297
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
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="put" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/support_draft_messages/{:id}/mark_read" %}
{% api-method-summary %}
mark read
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
    "type": "support_draft_messages",
    "links": {
      "self": "/rapi/v1/support_draft_messages/2"
    },
    "attributes": {
      "message_content": "Message Content",
      "kind": "text",
      "settings": {},
      "status": "approved",
      "resolved_time_unix": 1542682297,
      "comment": null,
      "create_user_resolved_read_time_unix": 1542682346,
      "created_at_unix": 1542603677,
      "updated_at_unix": 1542682346
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
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}
