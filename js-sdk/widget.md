# widget

### 概要

チャットウィジェットを表示するためのJavascript APIです。

* JS SDKのoptions部分にログイン情報やユーザ情報を追加できます。
* ユーザ情報は接客管理サイトの「来訪者詳細」に表示されます。
* ユーザ情報のキーワードは接客管理サイトの「マスターキーワード」に自動登録されます。

### 対象

* 来訪者用のチャットウィジェットを導入するウェブサイトがある
* HTML / JavaScriptに関する基本的な知識がある

## JS SDKの導入

1. JS SDKの読み込み
2. チャットウィジェットの表示

### JS SDKの読み込み方法

```markup
<script src="https://cdn.ok-sky.com/js/multi/widget.js" type="text/javascript"></script>
```

* `<head></head>` 内に記載

### チャットウィジェットの表示方法

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
  * ウィジェットIDは、接客管理サイトにて、「ウィジェット」管理ページにて、取得することができます。
* ② OK SKYシステムのURL
  * 接客管理サイトのURLから取得することができます。
  * `https://から始まり、/で終わる` 形で、 `https://{OK SKYシステムのFQDN}/` の形になります。

### GA\(Google Analytics\)でトラッキングする

```javascript
<script>
window.onload = function() {
  var chatWidget = new OkskyChat("ウィジェットID", "OK SKYシステムのURL", {'ga_client_code':'トラッキングコード'});
  chatWidget.show();
}
</script>
```

* オプションとして、 `ga_client_code` をキーとして、トラッキングコードを設定します。

## ログイン情報 / ユーザ情報の追加方法

ログイン方法やユーザ情報は `OkskyChat()` 関数の第三引数に追加します。 上の導入手順のコードに当てはめた場合、以下のようになります。

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

### ログイン情報

* `login: {}` 内に `key: value` の形で追加します。
* `key` 及び `value` は任意の値を設定できるため、チャットウィジェットを導入するウェブサービス内の顧客情報も使用可能です。
  * 例1\) `user_id: 123`
  * 例2\) `account_code: "ABCDE12345"`
* ログイン情報は顧客を識別するための情報なので、ユーザ毎に一意になるよう設定してください。

### ユーザ情報

* `user_infos: {}` 内に `key: value` の形で追加します。
* `key` 及び `value` は任意の値を設定できるため、チャットウィジェットを導入するウェブサービス内の顧客情報も使用可能です。

## チャットウィジェットを開く・閉じる

| API | 概要 |
| :--- | :--- |
| chatWidget.widget.open\(room\_id\(String\)\) | 特定のルームを指定してチャットウィジェットを表示する |
| chatWidget.widget.close | チャットウィジェットを非表示にする |

## コールバックを受け取る

| コールバックAPI | 概要 |
| :--- | :--- |
| chatWidget.widget.onReady | ウィジェットが利用できるようになった時のコールバック |
| chatWidget.event.onReceivedMessage | 現在開いているサポートでメッセージを受信した時のコールバック |
| chatWidget.event.onReceivedSomeMessage | 現在開いているサポートを含む、すべてのサポートのいずれかでメッセージを受信した時のコールバック |

例\)

```javascript
<button id="chat_btn">チャットで相談</button>

<script>
  var chatWidget;
  window.onload = function() {
    chatWidget = new OkskyChat("fuku-6123606CD9858E57", "http://fuku.ok-sky.net/", {
      login: {
        customer_code: "123456789"
      },
      user_infos: {
          customer_code: "123456789",
          live_in: "tokyo",
          age: "12",
          sex: "boy",
          user_id: 1,
      },
      'ga_client_code': 'GTM-XXXX'
    });
    chatWidget.widget.onReady = function() {
      // ウィジェットが利用できるようになった時
      console.log('onReady !!!!!!!!!');
    }

    chatWidget.event.onReceivedMessage = function(msg) {
      // 現在開いているサポートでメッセージを受信した時
      console.log('onReceivedMessage!!!!!!!!!!!!!!!!!!!', msg);
      alert('onReceivedMessage')
    }

    chatWidget.event.onReceivedSomeMessage = function(msg) {
      // 現在開いているサポートを含む、すべてのサポートのいずれかでメッセージを受信した時
      console.log('onReceivedSomeMessage!!!!!!!!!!!!!!!!!!!', msg);
      alert('onReceivedSomeMessage')
    }

    chatWidget.show();
    
    document.getElementById('chat_btn').addEventListener('click', function (event) {
      // 自ら用意したボタンを用いてメッセージを作成する。
      chatWidget.postMessage(null, "テストメッセージ", function (room) {
        chatWidget.widget.open(room.id.toString()); // チャットウィジェット表示する
      });
    }
  }
</script>
```

## ビルトイン関数

### 他のイベント（クリック等）をトリガーにしてメッセージを送る

**chatWidget.postMessage\(roomName, message, callback\);**

```javascript
<script>
window.onload = function() {
  var chatWidget = new OkskyChat("ウィジェットID", "OK SKYシステムのURL", {});
  var postMessageButton = document.getElementById("post_message");
  postMessageButton.addEventListener("click", function(event){
    chatWidget.postMessage(null, "メッセージ内容", function(room){
      // 投稿したサポートルームの情報 (room) に対する処理
    });
  });
}
</script>
```

得られる結果（room）のサンプル

```javascript
{
  awaiting_support: true,
  client_id: 1,
  create_user_id: 1,
  created_at: "2020-01-01T10:10:10.111+09:00",
  description: null,
  enabled: null,
  external_service_id: null,
  helped_room_id: null,
  id: 1,
  is_private: false,
  kind: "support_room",
  latest_message_id: 1,
  name: "sample-room-name-nEdOtD4RsN4",
  room_code: null,
  settings: {
    message_classify: true,
    message_dialog: false
  },
  updated_at: "2020-01-01T10:10:10.111+09:00"
}
```

* ① roomName: string
  * サポートルーム名 `room.name` を指定します。指定しない場合、新規サポートルームにメッセージが送信されます。
* ② message: string
  * 送信するメッセージを指定します。
* ③ callback: function
  * メッセージの送信に成功した場合に、実行する処理を記述できます。メッセージを送信したサポートルーム `room` の内容を参照することができます。

### 現在のサポートルーム一覧を取得する

**chatWidget.rooms\(callback\);**

```javascript
<script>
window.onload = function() {
  var chatWidget = new OkskyChat("ウィジェットID", "OK SKYシステムのURL", {});
  chatWidget.rooms(function(response){
    // サポートルーム一覧 (response.data) に対する処理
  });
}
</script>
```

得られる結果（response.data）のサンプル

```javascript
[
  { id: 1, name: "sample-room-name-1nEdOtDARsN" },
  { id: 2, name: "sample-room-name-2nEdOtDARsN" },
  { id: 3, name: "sample-room-name-3nEdOtDARsN" }
]
```

* ① callback: function
  * サポートルーム一覧の取得に成功した場合に、実行する処理を記述できます。  

### サポートルームと未読メッセージ件数の一覧を取得する

**chatWidget.unreadMessageCount\(roomId, callback\);**

```javascript
<script>
window.onload = function() {
  var chatWidget = new OkskyChat("ウィジェットID", "OK SKYシステムのURL", {});
  var roomId = 1;
  chatWidget.unreadMessageCount(roomId, function(entry){
    // サポートルームと未読メッセージ件数 (entry) に対する処理
  });
}
</script>
```

得られる結果（entry）のサンプル

```javascript
{
  room_id: 1,
  unread_message_counts: 2
}
```

* ① roomId: number
  * `chatWidget.rooms` で取得したサポートルームの ID `room.id` を指定します。
* ② callback: function
  * サポートルームと未読メッセージ件数の取得に成功した場合に、実行する処理を記述できます。  

## ビルトイン関数サンプル

### いずれかのサポートルームでメッセージを受信した場合、サポートルームごとの未読件数を取得する

```javascript
window.onload = function() {
  var chatWidget = new OkskyChat("fuku-6123606CD9858E57", "http://fuku.ok-sky.net/", {'ga_client_code':'GTM-XXXX'});
  chatWidget.show();
  chatWidget.event.onReceivedSomeMessage = function(event) {
    handleReceivedSomeMessage(event);
  };
  function handleReceivedSomeMessage(event) {
    chatWidget.rooms(function(response){
      if (response.data.length != 0) {
        response.data.forEach(function(room) {
          chatWidget.unreadMessageCount(room.id, function(entry){
            // サポートルームの ID と未読件数を取得
            console.log("room_id:", entry.room_id);
            console.log("unread_message_counts:", entry.unread_message_counts);
          });
        });
      }
    });
  };
});
```

