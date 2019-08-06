#### 概要

チャットウィジェットを表示するためのJavascript APIです。

* JS SDKのoptions部分にログイン情報やユーザ情報を追加できます。
* ユーザ情報は接客管理サイトの「来訪者詳細」に表示されます。
* ユーザ情報のキーワードは接客管理サイトの「マスターキーワード」に自動登録されます。

#### 対象
* 来訪者用のチャットウィジェットを導入するウェブサイトがある
* HTML / JavaScriptに関する基本的な知識がある

***

### JS SDKの導入

1. JS SDKの読み込み
2. チャットウィジェットの表示

#### JS SDKの読み込み方法

```html
<script src="https://cdn.ok-sky.com/sdk/latest/widget.js" type="text/javascript"></script>
```
* `<head></head>` 内に記載

#### チャットウィジェットの表示方法

```javascript
<script>
window.onload = function() {
  var chatWidget = new OkskyChat("ウィジェットID", "OK SKYシステムのURL", {});
  chatWidget.show();
}
</script>
```
* `<body>` 直後に記載
* ① ウィジェットID
    - ウィジェットIDは、接客管理サイトにて、「ウィジェット」管理ページにて、取得することができます。
* ② OK SKYシステムのURL
    - 接客管理サイトのURLから取得することができます。
    - `https://から始まり、/で終わる` 形で、 `https://{OK SKYシステムのFQDN}/` の形になります。

***

### ログイン情報 / ユーザ情報の追加方法

ログイン方法やユーザ情報は `OkskyChat()` 関数の第三引数に追加します。
上の導入手順のコードに当てはめた場合、以下のようになります。

```javascript
<script>
window.onload = function() {
  var chatWidget = new OkskyChat("ウィジェットID", "OK SKYシステムのURL", {
    login: { // <-------------------- ログイン情報
      customer_code: "123456789"
    },
    user_infos: { // <--------------- ユーザ情報
      customer_code: "123456789",
      live_in: "tokyo",
      age: "12",
      sex: "boy"
    }
  });
  chatWidget.show();
}
</script>
```

#### ログイン情報

* `login: {}` 内に `key: value` の形で追加します。
* `key` 及び `value` は任意の値を設定できるため、チャットウィジェットを導入するウェブサービス内の顧客情報も使用可能です。
    - 例1) `user_id: 123`
    - 例2) `account_code: "ABCDE12345"`
* ログイン情報は顧客を識別するための情報なので、ユーザ毎に一意になるよう設定してください。

#### ユーザ情報
* `user_infos: {}` 内に `key: value` の形で追加します。
* `key` 及び `value` は任意の値を設定できるため、チャットウィジェットを導入するウェブサービス内の顧客情報も使用可能です。

### チャットウィジェットを開く・閉じる

| API | 概要 |
|----|----|
| chatWidget.widget.open | チャットウィジェットを表示する |
| chatWidget.widget.close | チャットウィジェットを非表示にする |

### コールバックを受け取る

| コールバックAPI | 概要 |
|----|----|
| chatWidget.widget.onReady | ウィジェットが利用できるようになった時のコールバック |
| chatWidget.event.onReceivedMessage | メッセージを受信した時のコールバック |


例)

```javascript
<script>
  var chatWidget;
  window.onload = function() {
    chatWidget = new OkskyChat("shimizu-6123606CD9858E57", "http://shimizu.lvh.me:3000/", {
      login: {
        customer_code: "123456789"
      },
      user_infos: {
          customer_code: "123456789",
          live_in: "tokyo",
          age: "12",
          sex: "boy",
          user_id: 1,
      }
    });
    chatWidget.widget.onReady = function() {
      console.log('onReady !!!!!!!!!');
      chatWidget.widget.open();
    }

    chatWidget.event.onReceivedMessage = function(msg) {
      console.log('onReceivedMessage!!!!!!!!!!!!!!!!!!!', msg);
      alert('onReceivedMessage')
    }

    chatWidget.show();
  }
</script>
```
