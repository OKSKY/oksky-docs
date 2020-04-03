# kind of messages event

メッセージが送信されたことを示すEvent Objectです。

| Field | Type | Description |
| :--- | :--- | :--- |
| id | integer | メッセージ固有のID |
| room\_id | integer | ルーム固有のID |
| content | text | チャットテキストコンテント |
| user\_id | integer | 作成ユーザー固有のID |
| created\_at | datetime | 作成日時 |
| updated\_at | datetime | 更新日時 |
| kind | integer | メッセージタイプ `text`, `image`, `link` など |
| settings | object | 設定情報 |
| status | integer | `posted` のみ |
| posted\_at | datetime | 送信日時 |
| drive\_id | string |  |
| info | text |  |
| stamp\_id | string |  |
| deleted\_at | datetime | 削除日時 |
| tags | string |  |

_Sample kind: text_

```text
{
  "id":10305,
  "room_id":3157,
  "content":"テストメッセージその１",
  "user_id":1421,
  "created_at":"2017-09-20T18:48:21.797+09:00",
  "updated_at":"2017-09-20T18:48:21.797+09:00",
  "kind":"text",
  "settings":{},
  "status":"posted",
  "posted_at":"2017-09-20T18:48:21.789+09:00",
  "drive_id":null,
  "info":{},
  "stamp_id":null,
  "deleted_at":null,
  "tags":[]
}
```

_Sample kind: image_

```text
{
  "id":10293,
  "room_id":2424,
  "content":null,
  "user_id":1242,
  "created_at":"2017-09-19T20:21:30.851+09:00",
  "updated_at":"2017-09-19T20:21:30.851+09:00",
  "kind":"image",
  "settings":{
    "src_url":"https://hogehoge.cloudfront.net/attachments/hogehoge/store/hogehoge/hogehoge.jpg",
    "alt":"hogehoge.jpg",
    "type":"image/jpeg"
  },
  "status":"posted",
  "posted_at":"2017-09-19T20:21:29.040+09:00",
  "drive_id":"2060",
  "info":{},
  "stamp_id":null,
  "deleted_at":null,
  "tags":[]
}
```

