# Webhook

## Overview

メッセージの作成や、更新などの イベント は、接客管理サイト上のWebHookとして設定された送信先URL宛に HTTP POSTリクエスト で通知がされます。WebHookの設定にご不明点がございましたら、サポートにご連絡ください。

## Request headers

| Request | Description |
| :--- | :--- |
| User-Agent | Oksky-Hookshot/YOUR\_OKSKY\_DOMAIN |
| X-Oksky-Secret-Token | WebHookとして設定されたシークレットキー情報 |
| X-Oksky-App-Subdomain | YOUR\_OKSKY\_DOMAIN |
| Content-Type | WebHookとして設定されてたコンテントタイプに応じて、 `application/json`, `multipart/form-data`, `application/x-www-form-urlencoded`, `application/vnd.api+json` |

## Request body

ebHookとして設定されてたコンテントタイプに応じて、webhook event objectが含まれます。

## Response

常にHTTP HEAD status code `200` を返してください。

_INFO:_ HTTP POSTリクエストが何らかの理由で失敗しても、リクエストの再送信はされません。

