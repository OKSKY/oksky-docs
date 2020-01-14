# User object

## Fields

| Field | Type | Description | Editable |
| :--- | :--- | :--- | :--- |
| uuid | string |  |  |
| username | string |  |  |
| full_name | string |  |  |
| name | string |  |  |
| gravatar_id | string |  |  |
| email | string |  |  |
| avatar_url | string |  |  |
| default_avatar_url | string |  |  |
| user_type | string |  |  |
| status | string |  |  |
| max_support_count | integer |  |  |
| timezone | string |  |  |
| in_training | boolean |  |  |
| is_active | boolean |  |  |
| created_at | string |  |  |
| created_at_unix | integer |  |  |
| language | string |  |  |
| info | string |  |  |

## Filters

| Field | Description |
| :--- | :--- |
| id | ID |
| uuid |  |

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/9012e3b8a606555cc81d)

{% api-method method="get" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/{:id}" %}
{% api-method-summary %}
find user
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
        "id": "213",
        "type": "users",
        "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/213"
        },
        "attributes": {
            "last_seen_location": "https://{YOUR_OKSKY_DOMAIN}/clients/1/test",
            "recent_room_id": "184",
            "uuid": "3777489e-933f-45f5-8070-bb6c1ec65671",
            "username": "1911111455373228",
            "full_name": null,
            "name": "1911111455373228",
            "gravatar_id": "",
            "email": null,
            "avatar_url": null,
            "default_avatar_url": "https://www.oksky-chat.net/img/av1.png",
            "user_type": "Customer",
            "status": "offline",
            "max_support_count": 0,
            "active_supports_count": 0,
            "timezone": "Europe/Berlin",
            "in_training": null,
            "is_active": true,
            "created_at": "2019-11-11T23:55:37.455+09:00",
            "created_at_unix": 1573484137,
            "language": "ja",
            "sound_notification": true,
            "info": {
                "gender": "1",
                "country": "japan"
            },
            "notification_email": null
        },
        "relationships": {
            "user_widget_settings": {
                "links": {
                    "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/213/relationships/user_widget_settings",
                    "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/213/user_widget_settings"
                }
            },
            "draft_messages": {
                "links": {
                    "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/213/relationships/draft_messages",
                    "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/213/draft_messages"
                }
            },
            "present_rooms": {
                "links": {
                    "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/213/relationships/present_rooms",
                    "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/213/present_rooms"
                }
            },
            "support_rooms": {
                "links": {
                    "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/213/relationships/support_rooms",
                    "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/213/support_rooms"
                }
            },
            "members": {
                "links": {
                    "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/213/relationships/members",
                    "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/213/members"
                }
            },
            "supports": {
                "links": {
                    "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/213/relationships/supports",
                    "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/213/supports"
                }
            },
            "rooms": {
                "links": {
                    "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/213/relationships/rooms",
                    "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/213/rooms"
                }
            },
            "user_supported": {
                "links": {
                    "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/213/relationships/user_supported",
                    "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/213/user_supported"
                }
            },
            "memos": {
                "links": {
                    "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/213/relationships/memos",
                    "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/213/memos"
                }
            },
            "user_events": {
                "links": {
                    "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/213/relationships/user_events",
                    "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/213/user_events"
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

{% api-method method="get" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users" %}
{% api-method-summary %}
search users
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
      "type": "administrators",
      "links": {
        "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/administrators/1"
      },
      "attributes": {
        "uuid": "662696ae-5c8a-44ba-b36d-df1769b24c86",
        "username": "Manager",
        "full_name": null,
        "name": "Manager",
        "gravatar_id": "bb48e5ca314e44e0fb0ef522ca453e44",
        "email": "manager@ok-sky.com",
        "avatar_url": null,
        "default_avatar_url": "https://oksky-chat.herokuapp.com/img/av2.png",
        "user_type": "Administrator",
        "status": "offline",
        "max_support_count": 15,
        "timezone": "Asia/Tokyo",
        "in_training": null,
        "is_active": true,
        "created_at": "2018-11-19T13:43:16.066+09:00",
        "created_at_unix": 1542602596,
        "language": "jp"
      },
      "relationships": {
        "support_draft_messages": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/administrators/1/relationships/support_draft_messages",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/administrators/1/support_draft_messages"
          }
        },
        "present_rooms": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/administrators/1/relationships/present_rooms",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/administrators/1/present_rooms"
          },
          "data": [
            {
              "type": "rooms",
              "id": "3"
            },
            {
              "type": "rooms",
              "id": "5"
            },
            {
              "type": "rooms",
              "id": "6"
            },
            {
              "type": "rooms",
              "id": "1"
            }
          ]
        },
        "support_rooms": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/administrators/1/relationships/support_rooms",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/administrators/1/support_rooms"
          },
          "data": [
            {
              "type": "rooms",
              "id": "1"
            },
            {
              "type": "rooms",
              "id": "1"
            },
            {
              "type": "rooms",
              "id": "1"
            }
          ]
        },
        "members": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/administrators/1/relationships/members",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/administrators/1/members"
          },
          "data": [
            {
              "type": "members",
              "id": "2"
            },
            {
              "type": "members",
              "id": "3"
            },
            {
              "type": "members",
              "id": "5"
            },
            {
              "type": "members",
              "id": "7"
            }
          ]
        },
        "supports": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/administrators/1/relationships/supports",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/administrators/1/supports"
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
        "rooms": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/administrators/1/relationships/rooms",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/administrators/1/rooms"
          },
          "data": [
            {
              "type": "rooms",
              "id": "2"
            },
            {
              "type": "rooms",
              "id": "3"
            },
            {
              "type": "rooms",
              "id": "5"
            }
          ]
        },
        "starred_rooms": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/administrators/1/relationships/starred_rooms",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/administrators/1/starred_rooms"
          },
          "data": []
        },
        "starred_customers": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/administrators/1/relationships/starred_customers",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/administrators/1/starred_customers"
          },
          "data": []
        }
      }
    },
    {
      "id": "2",
      "type": "customers",
      "links": {
        "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/customers/2"
      },
      "attributes": {
        "uuid": "93ac8829-55c4-43bf-ae8c-a3c646110765",
        "username": "1811191347261665",
        "full_name": null,
        "name": "1811191347261665",
        "gravatar_id": "",
        "email": "guest_20181119134726167_36@fukushi-local-co.ok-sky.com",
        "avatar_url": null,
        "default_avatar_url": "https://oksky-chat.herokuapp.com/img/av1.png",
        "user_type": "Customer",
        "status": "offline",
        "max_support_count": 0,
        "timezone": "Asia/Tokyo",
        "in_training": null,
        "is_active": true,
        "created_at": "2018-11-19T13:47:26.276+09:00",
        "created_at_unix": 1542602846,
        "language": "jp",
        "last_seen_location": "https://{YOUR_OKSKY_DOMAIN}/clients/1/test",
        "recent_room_id": "1"
      },
      "relationships": {
        "support_draft_messages": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/customers/2/relationships/support_draft_messages",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/customers/2/support_draft_messages"
          }
        },
        "present_rooms": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/customers/2/relationships/present_rooms",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/customers/2/present_rooms"
          },
          "data": [
            {
              "type": "rooms",
              "id": "1"
            }
          ]
        },
        "support_rooms": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/customers/2/relationships/support_rooms",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/customers/2/support_rooms"
          },
          "data": []
        },
        "members": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/customers/2/relationships/members",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/customers/2/members"
          },
          "data": [
            {
              "type": "members",
              "id": "1"
            }
          ]
        },
        "supports": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/customers/2/relationships/supports",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/customers/2/supports"
          },
          "data": []
        },
        "rooms": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/customers/2/relationships/rooms",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/customers/2/rooms"
          },
          "data": [
            {
              "type": "rooms",
              "id": "1"
            }
          ]
        },
        "starred_rooms": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/customers/2/relationships/starred_rooms",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/customers/2/starred_rooms"
          },
          "data": []
        },
        "starred_customers": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/customers/2/relationships/starred_customers",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/customers/2/starred_customers"
          },
          "data": []
        },
        "user_supported": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/customers/2/relationships/user_supported",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/customers/2/user_supported"
          }
        },
        "memos": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/customers/2/relationships/memos",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/customers/2/memos"
          }
        },
        "user_events": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/customers/2/relationships/user_events",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/customers/2/user_events"
          }
        },
        "user_infos": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/customers/2/relationships/user_infos",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/customers/2/user_infos"
          }
        }
      }
    }
  ],
  "meta": {
    "record_count": 2
  },
  "links": {
    "first": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users?page%5Bnumber%5D=1&page%5Bsize%5D=25",
    "last": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users?page%5Bnumber%5D=1&page%5Bsize%5D=25"
  }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users" %}
{% api-method-summary %}
create user
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
    "type": "users",
    "links": {
      "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/4"
    },
    "attributes": {
      "uuid": "91c5ecb9-a94a-4c95-83f1-0c0ec0d3ecad",
      "username": "name",
      "full_name": null,
      "name": "name",
      "gravatar_id": "0ffd6652628fb7db3b6fd8b5606be357",
      "email": "email@solairo.co.jp",
      "avatar_url": null,
      "default_avatar_url": "https://oksky-chat.herokuapp.com/img/av2.png",
      "user_type": "Customer",
      "status": "offline",
      "max_support_count": 15,
      "timezone": "Asia/Tokyo",
      "in_training": null,
      "is_active": true,
      "created_at": "2018-11-20T13:08:45.351+09:00",
      "created_at_unix": 1542686925,
      "language": "jp"
    },
    "relationships": {
      "support_draft_messages": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/4/relationships/support_draft_messages",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/4/support_draft_messages"
        }
      },
      "present_rooms": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/4/relationships/present_rooms",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/4/present_rooms"
        },
        "data": []
      },
      "support_rooms": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/4/relationships/support_rooms",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/4/support_rooms"
        },
        "data": []
      },
      "members": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/4/relationships/members",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/4/members"
        },
        "data": []
      },
      "supports": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/4/relationships/supports",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/4/supports"
        },
        "data": []
      },
      "rooms": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/4/relationships/rooms",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/4/rooms"
        },
        "data": []
      },
      "starred_rooms": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/4/relationships/starred_rooms",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/4/starred_rooms"
        },
        "data": []
      },
      "starred_customers": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/4/relationships/starred_customers",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/4/starred_customers"
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

{% api-method method="put" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/{:id}" %}
{% api-method-summary %}
update users
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
    "type": "administrators",
    "links": {
      "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/administrators/1"
    },
    "attributes": {
      "uuid": "662696ae-5c8a-44ba-b36d-df1769b24c86",
      "username": "Manager",
      "full_name": null,
      "name": "Manager",
      "gravatar_id": "bb48e5ca314e44e0fb0ef522ca453e44",
      "email": "manager@ok-sky.com",
      "avatar_url": null,
      "default_avatar_url": "https://oksky-chat.herokuapp.com/img/av2.png",
      "user_type": "Administrator",
      "status": "offline",
      "max_support_count": 15,
      "timezone": "Asia/Tokyo",
      "in_training": null,
      "is_active": true,
      "created_at": "2018-11-19T13:43:16.066+09:00",
      "created_at_unix": 1542602596,
      "language": "jp"
    },
    "relationships": {
      "support_draft_messages": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/administrators/1/relationships/support_draft_messages",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/administrators/1/support_draft_messages"
        }
      },
      "present_rooms": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/administrators/1/relationships/present_rooms",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/administrators/1/present_rooms"
        },
        "data": [
          {
            "type": "rooms",
            "id": "3"
          },
          {
            "type": "rooms",
            "id": "5"
          },
          {
            "type": "rooms",
            "id": "6"
          },
          {
            "type": "rooms",
            "id": "1"
          }
        ]
      },
      "support_rooms": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/administrators/1/relationships/support_rooms",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/administrators/1/support_rooms"
        },
        "data": [
          {
            "type": "rooms",
            "id": "1"
          },
          {
            "type": "rooms",
            "id": "1"
          },
          {
            "type": "rooms",
            "id": "1"
          }
        ]
      },
      "members": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/administrators/1/relationships/members",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/administrators/1/members"
        },
        "data": [
          {
            "type": "members",
            "id": "2"
          },
          {
            "type": "members",
            "id": "3"
          },
          {
            "type": "members",
            "id": "5"
          },
          {
            "type": "members",
            "id": "7"
          }
        ]
      },
      "supports": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/administrators/1/relationships/supports",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/administrators/1/supports"
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
      "rooms": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/administrators/1/relationships/rooms",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/administrators/1/rooms"
        },
        "data": [
          {
            "type": "rooms",
            "id": "2"
          },
          {
            "type": "rooms",
            "id": "3"
          },
          {
            "type": "rooms",
            "id": "5"
          }
        ]
      },
      "starred_rooms": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/administrators/1/relationships/starred_rooms",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/administrators/1/starred_rooms"
        },
        "data": []
      },
      "starred_customers": {
        "links": {
          "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/administrators/1/relationships/starred_customers",
          "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/administrators/1/starred_customers"
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

{% api-method method="delete" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/{:id}" %}
{% api-method-summary %}
delete user
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

{% api-method method="patch" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/reactivate" %}
{% api-method-summary %}
reactivate
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
      "type": "users",
      "links": {
        "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/1"
      },
      "attributes": {
        "uuid": "662696ae-5c8a-44ba-b36d-df1769b24c86",
        "username": "Manager",
        "full_name": null,
        "name": "Manager",
        "gravatar_id": "bb48e5ca314e44e0fb0ef522ca453e44",
        "email": "manager@ok-sky.com",
        "avatar_url": null,
        "default_avatar_url": "https://oksky-chat.herokuapp.com/img/av2.png",
        "user_type": "Administrator",
        "status": "offline",
        "max_support_count": 15,
        "timezone": "Asia/Tokyo",
        "in_training": null,
        "is_active": true,
        "created_at": "2018-11-19T13:43:16.066+09:00",
        "created_at_unix": 1542602596,
        "language": "jp"
      },
      "relationships": {
        "support_draft_messages": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/1/relationships/support_draft_messages",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/1/support_draft_messages"
          }
        },
        "present_rooms": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/1/relationships/present_rooms",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/1/present_rooms"
          },
          "data": [
            {
              "type": "rooms",
              "id": "3"
            },
            {
              "type": "rooms",
              "id": "5"
            },
            {
              "type": "rooms",
              "id": "6"
            },
            {
              "type": "rooms",
              "id": "1"
            }
          ]
        },
        "support_rooms": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/1/relationships/support_rooms",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/1/support_rooms"
          },
          "data": [
            {
              "type": "rooms",
              "id": "1"
            },
            {
              "type": "rooms",
              "id": "1"
            },
            {
              "type": "rooms",
              "id": "1"
            }
          ]
        },
        "members": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/1/relationships/members",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/1/members"
          },
          "data": [
            {
              "type": "members",
              "id": "2"
            },
            {
              "type": "members",
              "id": "3"
            },
            {
              "type": "members",
              "id": "5"
            },
            {
              "type": "members",
              "id": "7"
            }
          ]
        },
        "supports": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/1/relationships/supports",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/1/supports"
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
        "rooms": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/1/relationships/rooms",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/1/rooms"
          },
          "data": [
            {
              "type": "rooms",
              "id": "2"
            },
            {
              "type": "rooms",
              "id": "3"
            },
            {
              "type": "rooms",
              "id": "5"
            }
          ]
        },
        "starred_rooms": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/1/relationships/starred_rooms",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/1/starred_rooms"
          },
          "data": []
        },
        "starred_customers": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/1/relationships/starred_customers",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/1/starred_customers"
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
    "first": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users?page%5Bnumber%5D=1&page%5Bsize%5D=25",
    "last": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users?page%5Bnumber%5D=1&page%5Bsize%5D=25"
  }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="patch" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/deactivate" %}
{% api-method-summary %}
deactivate
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
      "type": "users",
      "links": {
        "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/1"
      },
      "attributes": {
        "uuid": "662696ae-5c8a-44ba-b36d-df1769b24c86",
        "username": "Manager",
        "full_name": null,
        "name": "Manager",
        "gravatar_id": "bb48e5ca314e44e0fb0ef522ca453e44",
        "email": "manager@ok-sky.com",
        "avatar_url": null,
        "default_avatar_url": "https://oksky-chat.herokuapp.com/img/av2.png",
        "user_type": "Administrator",
        "status": "offline",
        "max_support_count": 15,
        "timezone": "Asia/Tokyo",
        "in_training": null,
        "is_active": true,
        "created_at": "2018-11-19T13:43:16.066+09:00",
        "created_at_unix": 1542602596,
        "language": "jp"
      },
      "relationships": {
        "support_draft_messages": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/1/relationships/support_draft_messages",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/1/support_draft_messages"
          }
        },
        "present_rooms": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/1/relationships/present_rooms",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/1/present_rooms"
          },
          "data": [
            {
              "type": "rooms",
              "id": "3"
            },
            {
              "type": "rooms",
              "id": "5"
            },
            {
              "type": "rooms",
              "id": "6"
            },
            {
              "type": "rooms",
              "id": "1"
            }
          ]
        },
        "support_rooms": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/1/relationships/support_rooms",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/1/support_rooms"
          },
          "data": [
            {
              "type": "rooms",
              "id": "1"
            },
            {
              "type": "rooms",
              "id": "1"
            },
            {
              "type": "rooms",
              "id": "1"
            }
          ]
        },
        "members": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/1/relationships/members",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/1/members"
          },
          "data": [
            {
              "type": "members",
              "id": "2"
            },
            {
              "type": "members",
              "id": "3"
            },
            {
              "type": "members",
              "id": "5"
            },
            {
              "type": "members",
              "id": "7"
            }
          ]
        },
        "supports": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/1/relationships/supports",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/1/supports"
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
        "rooms": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/1/relationships/rooms",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/1/rooms"
          },
          "data": [
            {
              "type": "rooms",
              "id": "2"
            },
            {
              "type": "rooms",
              "id": "3"
            },
            {
              "type": "rooms",
              "id": "5"
            }
          ]
        },
        "starred_rooms": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/1/relationships/starred_rooms",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/1/starred_rooms"
          },
          "data": []
        },
        "starred_customers": {
          "links": {
            "self": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/1/relationships/starred_customers",
            "related": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/1/starred_customers"
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
    "first": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users?page%5Bnumber%5D=1&page%5Bsize%5D=25",
    "last": "https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users?page%5Bnumber%5D=1&page%5Bsize%5D=25"
  }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="put" host="" path="https://{YOUR_OKSKY_DOMAIN}/rapi/v1/users/{:id}/regenerate_access_token" %}
{% api-method-summary %}
regenerate access token
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
