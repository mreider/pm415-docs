---
description: 'These methods aloow you to create, delete and get info on subscribers.'
---

# /subscribers

{% api-method method="post" host="https://pm415.com" path="/api/subscribers/new/:ownertable/:ownerid" %}
{% api-method-summary %}
Create new subscriber
{% endapi-method-summary %}

{% api-method-description %}
Creates the new suscriber.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name=":ownerid" type="number" required=true %}
The ID of the bug or initiative or item
{% endapi-method-parameter %}

{% api-method-parameter name=":ownertable" type="string" required=true %}
"Bugs" or "Initiatives" or "Items"
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
Authorization: Bearer 50ca9ba0f7b1444fa55d5
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="" type="object" required=true %}
{"subowner": "comments", "subownerId": "72", "usersId": \["1","2"\]}  
to clear all subscribers function leave the "userid" empty
{% endapi-method-parameter %}

{% api-method-parameter name="" type="object" required=true %}
{"usersId": \["1","2"\]}
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "success": true
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://pm415.com" path="/api/subscribers/:ownertable/:ownerid" %}
{% api-method-summary %}
Get list of subscribers
{% endapi-method-summary %}

{% api-method-description %}
Gets the list of subscribers.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name=":ownerid" type="number" required=true %}
The ID of the bug or initiative or item
{% endapi-method-parameter %}

{% api-method-parameter name=":ownertable" type="string" required=true %}
"Bugs" or "Initiatives" or "Items"
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
Authorization: Bearer 50ca9ba0f7b1444fa55d5
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "success": true,
    "subscribers": [
        {
            "email": "nosuchip@gmail.com",
            "firstName": "Iddqd",
            "lastName": "Idkfa",
            "id": 1
        },
        {
            "email": "zverozabr@yandex.ru",
            "firstName": "Alex",
            "lastName": "Prilipko",
            "id": 2
        },
        {
            "email": "nosuchip@gmail.com",
            "firstName": "Iddqd",
            "lastName": "Idkfa",
            "id": 1
        },
        {
            "email": "zverozabr@yandex.ru",
            "firstName": "Alex",
            "lastName": "Prilipko",
            "id": 2
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://pm415.com" path="/api/subscribers/:ownertable/:ownerid/:subowner/:subownerid" %}
{% api-method-summary %}
Get list of subscribers
{% endapi-method-summary %}

{% api-method-description %}
Gets the list of subscribers on the selected comments.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name=":subownerid" type="number" required=true %}
The ID of the comment
{% endapi-method-parameter %}

{% api-method-parameter name=":subowner" type="string" required=true %}
"Comments" or another tablename
{% endapi-method-parameter %}

{% api-method-parameter name=":ownerid" type="number" required=true %}
The ID of the bug or initiative or item
{% endapi-method-parameter %}

{% api-method-parameter name=":ownertable" type="string" required=true %}
"Bugs" or "Initiatives" or "Items"
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
Authorization: Bearer 50ca9ba0f7b1444fa55d5
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "success": true,
    "subscribers": [
        {
            "email": "nosuchip@gmail.com",
            "firstName": "Iddqd",
            "lastName": "Idkfa",
            "id": 1
        },
        {
            "email": "zverozabr@yandex.ru",
            "firstName": "Alex",
            "lastName": "Prilipko",
            "id": 2
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://pm415.com" path="/api/subscribers/delete/:ownertable/:ownerid" %}
{% api-method-summary %}
Delete subscriber
{% endapi-method-summary %}

{% api-method-description %}
Deletes the current subscriber.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name=":ownerid" type="number" required=true %}
The ID of the bug or initiative or item
{% endapi-method-parameter %}

{% api-method-parameter name=":ownertable" type="string" required=true %}
"Bugs" or "Initiatives" or "Items"
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
Authorization: Bearer 50ca9ba0f7b1444fa55d5
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="" type="object" required=true %}
{"usersId": \["2"\]}
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "success": true
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

