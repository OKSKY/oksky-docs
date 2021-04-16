# kind of room event

## Room object

ルームが作成・更新されたことを示すEvent Objectです。

| Field | Type | Description |
| :--- | :--- | :--- |
| id | integer | ルーム固有のID |
| name | string | ルーム固有の名前 |
| created\_at | datatime | 作成日時 |
| updated\_at | datetime | 更新日時 |
| `create_user_id` | integer | 作成したユーザー固有のID |
| description | text | 詳細 |
| is\_private | boolean | 非公開か否か |
| settings | object | 設定 |
| kind | string | ルーム種別 |
| enabled | boolean | 有効か否か |
| client\_id | integer | ウィジェット固有のID |
| `external_service_id` | integer | コネクション固有のID |
| awaiting\_support | boolean | サポートアサイン待機中か否か |
| room\_code | string | ルーム固有のコード |
| `helped_room_id` | integer | ヘルプルーム固有のID |
| `latest_message_id` | integer | ルーム内で投稿された最終メッセージのID |

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

