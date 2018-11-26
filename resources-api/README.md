# Resources API

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

{% api-method method="get" host="https://{YOUR\_OKSKY\_DOMAIN}" path="/rapi/v1/rooms" %}
{% api-method-summary %}
GET Request Sample
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="X-Access-Token" type="string" required=true %}
your access token set here.
{% endapi-method-parameter %}

{% api-method-parameter name="Content-Type" type="string" required=true %}
application/vnd.api+json
{% endapi-method-parameter %}

{% api-method-parameter name="Accept" type="string" required=true %}
application/vnd.api+json
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
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

* page[] - ページパラメータはページ番号とレコード数を指定することができます。
  * number
    * ページ番号
    * デフォルトは `1`
  * size
    * １ページあたりのレコード数
    * デフォルトは `25`
    * 最大取得レコード数は `100`

* sort - カンマで区切られたフィールド名。降順で並び替える場合は、フィールド名に `-` をつける。

* fields[resource] - 関連リソース名を指定します。値はカンマで区切られた属性名。

* include - カンマで区切られた関連リソース名。

* filter[] - 属性名を指定します。

{% api-method method="post" host="https://{YOUR\_OKSKY\_DOMAIN}" path="/rapi/v1/rooms" %}
{% api-method-summary %}
Create Request Sample
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
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

### POST Request

POST（作成）リクエストとPUT（更新）リクエストには、JSONペイロードが必要です。

#### Example

```
data: {
  type: "rooms",
  attributes: {
    kind: "support_room"
  }
}
```

* data - 各リソースオブジェクトの内容を参照
  * type - リソース名
  * attributes - 属性名と値のハッシュ値。

{% api-method method="put" host="https://{YOUR\_OKSKY\_DOMAIN}" path="/rapi/v1/rooms/1" %}
{% api-method-summary %}
Edit Request Sample
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
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

### PUT Request

PUT（更新）リクエストには、JSONペイロードが必要です。

#### Example

```
data: {
  type: "rooms",
  id: "1",
  attributes: {
    kind: "support_room"
  }
}
```

* data - 各リソースオブジェクトの内容を参照
  * type - リソース名
  * id - 更新対象のリソースID。
  * attributes - 属性名と値のハッシュ値。

{% api-method method="delete" host="https://{YOUR\_OKSKY\_DOMAIN}" path="/rapi/v1/rooms/1" %}
{% api-method-summary %}
Delete Request Sample
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
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

### Delete Request

IDを持つレコードエンドポイントを指定します。

### Status codes

返す主要なstatus codeは以下です。

| Code | Description |
| :--- | :--- |
| 200 |	Success |
| 201 |	Success |
| 400 |	bad request |
| 401 |	unauthorized |
| 403 |	unauthorized |
| 404 |	not found |
| 405 |	not allowed |
| 406 |	not acceptable |
| 422 |	unprocessable entity |
| 500 |	standard error |
| 501 |	not implemented |

### Error responses

エラー時のresponse bodyは、以下のフィールドを持つJSONデータです

| Field | Type | Description |
| :--- | :--- | :--- |
| erros |	Object Array |
| errors[n].status | error code |
| errors[n].code | error code |
| errors[n].title | error title |
| errors[n].detail | error detail |

### Error messages

Error response JSONにおける errors[title] フィールドに設定される主要なエラーメッセージは以下です。

| Title | Description |
| :--- | :--- | :--- |
| Unauthorized | AccessTokenなど、認証に必要な情報の不足 |
| Invalid IP Address. Did you set the VALID_IPS environment variable? | リクエスト元IPアドレスが不正 |
