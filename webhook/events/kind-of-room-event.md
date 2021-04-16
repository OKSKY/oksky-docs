# kind of room event

## Room object

ルームが作成・更新されたことを示すEvent Objectです。

| Field | Type | Description |
| :--- | :--- | :--- |
| id | integer |  |
| name | string |  |
| created\_at | datatime |  |
| updated\_at | datetime |  |
| `create_user_id` | integer |  |
| description | text |  |
| is\_private | boolean |  |
| settings | object |  |
| kind | string |  |
| enabled | boolean |  |
| client\_id | integer |  |
| `external_service_id` | integer |  |
| awaiting\_support | boolean |  |
| room\_code | string |  |
| `helped_room_id` | integer |  |
| `latest_message_id` | integer |  |

sample:

```text
{
  "action": "update",
  "object_name": "Room",
  "object": {
    "id": 615,
    "name": "mantis-dazzling-twig-ewHBENNRs04",
    "created_at": "2021-03-17T14:27:04.386+09:00",
    "updated_at": "2021-03-17T14:27:55.311+09:00",
    "create_user_id": 689,
    "description": null,
    "is_private": false,
    "settings": {
      "message_classify": true,
      "message_dialog": false
    },
    "kind": "support_room",
    "enabled": null,
    "client_id": 1,
    "external_service_id": null,
    "room_code": null,
    "awaiting_support": false,
    "helped_room_id": null,
    "latest_message_id": 1384
  }
}
```

