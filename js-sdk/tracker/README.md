#### 概要

来訪者のトラッキングを行うためのJavascript APIです。

* チャットウィジェットと併用して利用します。
* チャットのやり取りをしている利用者がどのページを閲覧しているのか（PVトラッキング）を計測できます。
* コンバージョン等のイベントもトラッキングすることができます

#### 対象
* 来訪者用のチャットウィジェットを導入するウェブサイトがある
* HTML / JavaScriptに関する基本的な知識がある

***

### JS SDKの導入

1. JS SDKの読み込み
2. PV送信
3. 特定のイベント送信

#### JS SDKの読み込み方法

```html
<script src="https://cdn.ok-sky.com/sdk/latest/tracker.js" type="text/javascript"></script>
```
* `<head></head>` 内に記載

#### PV送信

```javascript
<script>
  let tracker = new oktag("OK SKYシステムのURL");
  tracker.send({command: "pageview"});
</script>
```
* `<body>` 直後に記載
* OK SKYシステムのURL
    - 接客管理サイトのURLから取得することができます。
    - `https://から始まり、/で終わる` 形で、 `https://{OK SKYシステムのFQDN}/` の形になります。

#### 特定のイベント送信

```javascript
<script>
  let tracker = new oktag("OK SKYシステムのURL");
  tracker.send({command: "event", action: "buy", category: "mens", label: "pants", value: 42});
</script>
```
* `<body>` 直後に記載
* OK SKYシステムのURL
    - 接客管理サイトのURLから取得することができます。
    - `https://から始まり、/で終わる` 形で、 `https://{OK SKYシステムのFQDN}/` の形になります。
* `command` は、 `"event"` で固定です。
    - `action` 、 `category` 、 `label` は文字列で任意の情報をしてできます。
    - `value` では、数字を指定してください。

