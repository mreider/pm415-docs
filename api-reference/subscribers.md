# /subscribers

{% api-method method="post" host="http://pm415.com:3000/api/subscribers/new/:ownerTable/:ownerId" path="" %}
{% api-method-summary %}
Create new subscriber
{% endapi-method-summary %}

{% api-method-description %}
Creates the new suscriber
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="ownerid" type="number" required=true %}
bug id, initiative id or item id
{% endapi-method-parameter %}

{% api-method-parameter name="ownertable" type="string" required=true %}
bugs, initiatives or items
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
Authorization: Bearer 50ca9ba0f7b1444fa55d5
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="" type="string" required=true %}
{"subowner": "comments", "subownerId": "72", "usersId": \["1","2"\]}  
to clear all subscribers function leave the "userid" empty
{% endapi-method-parameter %}

{% api-method-parameter name="" type="string" required=true %}
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

