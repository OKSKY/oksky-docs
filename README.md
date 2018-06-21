---
description: こちらの機能全てがベータリリースとして提供されています。今後変更が加えられることがございます。ご注意ください。
---

# OK SKY API Reference

## Resources API

### Overview

メッセージオブジェクトや、ユーザーオブジェクトなどのDB上に格納されている情報へのアクセスができるAPIです。

#### Dreaming in URL’s

```
https://{YOUR_OKSKY_DOMAIN}/rapi/v1/
```

{% hint style="info" %}
 YOUR\_OKSKY\_DOMAINは、テナント毎に発行されます。
{% endhint %}

Sample URLs

```
https://{YOUR_OKSKY_DOMAIN}.ok-sky.com/rapi/v1/{resource_name}https://{YOUR_OKSKY_DOMAIN}.ok-sky.com/rapi/v1/{resource_name}/{resource_id}https://{YOUR_OKSKY_DOMAIN}.ok-sky.com/rapi/v1/{resource_name}/relationships/{resource_name}https://{YOUR_OKSKY_DOMAIN}.ok-sky.com/rapi/v1/{resource_name}/relationships/{child_resource_name}/{child_resource_id}https://{YOUR_OKSKY_DOMAIN}.ok-sky.com/rapi/v1/roomshttps://{YOUR_OKSKY_DOMAIN}.ok-sky.com/rapi/v1/rooms/1/https://{YOUR_OKSKY_DOMAIN}.ok-sky.com/rapi/v1/rooms/1/relationships/messageshttps://{YOUR_OKSKY_DOMAIN}.ok-sky.com/rapi/v1/messageshttps://{YOUR_OKSKY_DOMAIN}.ok-sky.com/rapi/v1/messages/1
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

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

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

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

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

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

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

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

