# Resources object

## Overview

メッセージオブジェクトや、ユーザーオブジェクトなどのDB上に格納されている情報へのアクセスができるAPIです。

### Dreaming in URL’s

```text
https://{YOUR_OKSKY_DOMAIN}/rapi/v1/
```

{% hint style="info" %}
YOUR\_OKSKY\_DOMAINは、テナント毎に発行されます。
{% endhint %}

Sample URLs

```text
https://{YOUR_OKSKY_DOMAIN}.ok-sky.com/rapi/v1/{resource_name}
https://{YOUR_OKSKY_DOMAIN}.ok-sky.com/rapi/v1/{resource_name}/{resource_id}
https://{YOUR_OKSKY_DOMAIN}.ok-sky.com/rapi/v1/{resource_name}/relationships/{resource_name}
https://{YOUR_OKSKY_DOMAIN}.ok-sky.com/rapi/v1/{resource_name}/relationships/{child_resource_name}/{child_resource_id}
https://{YOUR_OKSKY_DOMAIN}.ok-sky.com/rapi/v1/rooms
https://{YOUR_OKSKY_DOMAIN}.ok-sky.com/rapi/v1/rooms/1/
https://{YOUR_OKSKY_DOMAIN}.ok-sky.com/rapi/v1/rooms/1/relationships/messages
https://{YOUR_OKSKY_DOMAIN}.ok-sky.com/rapi/v1/messages
https://{YOUR_OKSKY_DOMAIN}.ok-sky.com/rapi/v1/messages/1
```

### Fetch (GET) Requests

JSONAPIはフィルタリング、ページネーション、ソート、関連リソースを含むクエリ文字列パラメタを提供します。

#### Example

```
https://{YOUR_OKSKY_DOMAIN}.ok-sky.com/rapi/v1/rooms
  ?page[number]=2
  &page[size]=50
  &sort=create_user_id,-created
  &fields[users]=id,name,created_at
  &include=messages,create_user
  &filter[kind]=support_room
```

