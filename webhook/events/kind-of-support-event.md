# kind of support event

### Support Object

サポートが開始・終了したことを示すEvent Objectです。

| Field | Type | Description |
| :--- | :--- | :--- |
| id | integer | サポート固有のID |
| room\_id | integer | ルーム固有のID |
| start\_time | datetime | 開始日時 |
| end\_time | datetime | 終了日時 |
| created\_at | datetime | 作成日時 |
| updated\_at | datetime | 更新日時 |
| user\_id | integer | 担当している接客者固有のID |
| self\_comment | text | コメント |
| self\_evaluation | text | 評価 |



sample:

```text
{
  "action": "create",
  "object_name": "Support",
  "object": {
    "id": 259,
    "room_id": 615,
    "start_time": "2021-04-16T13:42:53.282+09:00",
    "end_time": null,
    "created_at": "2021-04-16T13:42:53.284+09:00",
    "updated_at": "2021-04-16T13:42:53.284+09:00",
    "user_id": 1,
    "self_comment": null,
    "self_evaluation": null
  }
}
```

