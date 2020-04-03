# Events

## Webhook event object

oksky-chat 上で発生したイベントを表すオブジェクトです。

* Common Fields
* Object

## Common Fields

全てのWebhook event objectには以下のフィールドが含まれます。

| Field | Type | Description |
| :--- | :--- | :--- |
| action | string | イベントの種類を表す識別子 example: create, update |
| object\_name | string | 対象オブシェクトの識別子 example: Message, Customer, User |
| object | object | オブジェクト |

_Sample_

```text
{
  "action":"create",
  "object_name":"Message",
  "object":{...}
}
```

