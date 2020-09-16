# widget

### 概要

任意のウェブサイトに、チャットウィジェットを表示するための JavaScript API です。

* ログイン情報やユーザ情報を追加できます。
* ユーザ情報は接客管理サイトの「来訪者詳細」に表示されます。
* ユーザ情報のキーワードは接客管理サイトの「マスターキーワード」に自動登録されます。

### 対象

* 来訪者用のチャットウィジェットを導入するウェブサイトがある
* HTML / JavaScript に関する基本的な知識がある

## JS SDK の導入

1. JS SDK の読み込み
2. チャットウィジェットの表示

### JS SDK の読み込み方法

```markup
<script src="https://cdn.ok-sky.com/sdk/multi/widget.js" type="text/javascript"></script>
```

* `<head></head>` 内に記載

### チャットウィジェットの表示方法

```javascript
<script>
window.onload = function() {
  var chatWidget = new OkskyChat("ウィジェット ID", "OK SKY システムの URL", {});
  chatWidget.show();
}
</script>
```

* `<body>` 直後に記載
* ① ウィジェット ID
  * ウィジェット ID は、接客管理サイトの「ウィジェット」管理ページで取得することができます。
* ② OK SKY システムの URL
  * 接客管理サイトの URL を指定します。
  * `https://から始まり、/で終わる` 形で、 `https://{OK SKYシステムの FQDN}/` の形になります。

### GA\(Google Analytics\) でトラッキングする

```javascript
<script>
window.onload = function() {
  var chatWidget = new OkskyChat("ウィジェット ID", "OK SKY システムの URL", {"ga_client_code", "トラッキング ID"});
  chatWidget.show();
}
</script>
```

* オプションに `{"ga_client_code", "トラッキングID"}` を設定します。
* トラッキング ID には Google アナリティクスで作成した `UA-********-*` 形式の文字列が入ります。

### チャットウィジェットを開くボタンを表示させないようにする

```javascript
<script>
window.onload = function() {
  var chatWidget = new OkskyChat("ウィジェットID", "OK SKYシステムのURL", {});
  chatWidget.show({"hideButton":true});
}
</script>
```

* チャットウィジェットを開くためのボタンとして、OK SKY が提供するデフォルトのボタンは表示せず、ご自身でデザインしたボタンを使いたい場合、この機能を利用します。
* `chatWidget.show()` の引数に `{"hideButton":true}` を指定することで、チャットウィジェットを開くボタンを表示させないようにすることができます。
* この引数を指定することでデフォルトのボタンは表示されなくなります。 `widget.onReady()` イベントのコールバックによって代わりのボタンを表示するとともに、そのボタンのイベントに `chatWidget.widget.open()` を割り当てる必要があります。
* チャットウィジェットを開くボタンとポップアップウィンドウのどちらも表示させない場合は `{"hideButton":true,"hidePopup":true}` のように指定します。

### ポップアップウィンドウを表示させないようにする

```javascript
<script>
window.onload = function() {
  var chatWidget = new OkskyChat("ウィジェットID", "OK SKYシステムのURL");
  chatWidget.show({"hidePopup":true});
}
</script>
```

* チャットウィジェットが閉じた状態でメッセージを受信した際、ポップアップウィンドウによって受信したメッセージが表示されますが、これを表示させない場合にこの機能を利用します。
* `chatWidget.show()` の引数に `{"hidePopup":true}` を指定することで、チャットウィジェットが閉じた状態でメッセージを受信した際に表示されるポップアップウィンドウを表示させないようにすることができます。
* チャットウィジェットを開くボタンとポップアップウィンドウのどちらも表示させない場合は `{"hideButton":true,"hidePopup":true}` のように指定します。

## ログイン情報 / ユーザ情報の追加方法

ログイン方法やユーザ情報は `OkskyChat()` 関数の第三引数 `options` に追加します。 上の導入手順のコードに当てはめた場合、以下のようになります。

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
| chatWidget.widget.open(roomId?) | チャットウィジェットを表示する ※チャットルームを指定して表示することも可能 |
| chatWidget.widget.close() | チャットウィジェットを非表示にする |

## コールバックを受け取る

| コールバックAPI | 概要 |
| :--- | :--- |
| chatWidget.widget.onReady(function) | ウィジェットが利用できるようになった時のコールバック |
| chatWidget.event.onReceivedMessage(function) | 現在開いているサポートでメッセージを受信した時のコールバック |
| chatWidget.event.onReceivedSomeMessage(function) | 現在開いているサポートを含む、すべてのサポートのいずれかでメッセージを受信した時のコールバック |

例\)

```javascript
<script>
  var chatWidget;
  window.onload = function() {
    chatWidget = new OkskyChat("ウィジェットID", "OK SKYシステムのURL", {
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
      console.log('🔥onReady');
      chatWidget.widget.open();
    }

    chatWidget.event.onReceivedMessage = function(msg) {
      console.log('🔥onReceivedMessage', msg);
      alert('onReceivedMessage')
    }

    chatWidget.event.onReceivedSomeMessage = function(msg) {
      console.log('🔥onReceivedSomeMessage', msg);
      alert('onReceivedSomeMessage')
    }

    chatWidget.show();
  }
</script>
```

## ビルトイン関数

### 他のイベント（クリック等）をトリガーにしてメッセージを送る

**chatWidget.postMessage(roomName, message, callback);**

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

**chatWidget.rooms(callback);**

```javascript
<script>
window.onload = function() {
  var chatWidget = new OkskyChat("ウィジェット ID", "OK SKY システムの URL", {});
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

**chatWidget.unreadMessageCount(roomId, callback);**

```javascript
<script>
window.onload = function() {
  var chatWidget = new OkskyChat("ウィジェット ID", "OK SKY システムの URL", {});
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
  var chatWidget = new OkskyChat("ウィジェット ID", "OK SKY システムの URL", {});
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

### デフォルトのボタン以外から自動メッセージを送信し、指定したサポートルームを開く

```html
<a href="#" id="chat_btn">メッセージを作成する & チャットを開く</a>
<a href="#" id="show_btn" style="display: none;">チャットを開く（room: <span id="room_id"></span>）</a>
```

```javascript
window.onload = function() {
  var chatWidget = new OkskyChat("ウィジェットID", "OK SKY システムの URL", {});
  chatWidget.show({"hideButton":true,"hidePopup":true});

  document.getElementById('chat_btn').addEventListener('click', function (event) {
    const okSkyWidgetElement = document.getElementById('ok-sky-widget');
    okSkyWidgetElement.style.display = "block";
    const message = "テスト自動メッセージ";
    chatWidget.postMessage(null, message, function(room) {
      let roomId = document.getElementById("room_id");
      let showBtn = document.getElementById("show_btn");
      roomId.innerHTML = room.id;
      chatWidget.widget.open(document.getElementById("room_id").innerHTML);
      showBtn.style.display = 'block';
    });
  }, false);

  document.getElementById('show_btn').addEventListener('click', function (event) {
    chatWidget.widget.open(document.getElementById("room_id").innerHTML);
  }, false);
}
```
