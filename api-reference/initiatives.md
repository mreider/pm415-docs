# /initiatives

{% api-method method="get" host="http://pm415.com/api/initiatives/all/:showarchived/:orgid" path="" %}
{% api-method-summary %}
Get initiatives list
{% endapi-method-summary %}

{% api-method-description %}
Gets the initiatives list
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="orgid" type="number" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="showarchived" type="string" required=true %}
true or falst
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
    "initiatives": [
        {
            "email": "hwyxlisjb@emlpro.com",
            "firstName": "alena",
            "lastName": "prilipko",
            "createdAt": "2019-04-27T07:05:58.000Z",
            "id": 25,
            "title": "Api created",
            "archived": 0,
            "description": "api created Description",
            "horizon": "2011-11-11T00:00:00.000Z",
            "createdBy": 13,
            "statusId": 9,
            "order_index": 0,
            "organizationId": 17,
            "popularity": 0
        }
    ],
    "admin": true
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="http://pm415.com:3000/api/initiatives/:orgId/:initiativeId" path="" %}
{% api-method-summary %}
Get current initiative
{% endapi-method-summary %}

{% api-method-description %}
Gets the current initiative information
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="initiativeid" type="number" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="orgid" type="number" required=true %}

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
    "initiative": {
        "createdAt": "2019-04-27T07:05:58.000Z",
        "id": 25,
        "title": "Api created",
        "archived": 0,
        "description": "api created Description",
        "horizon": "2011-11-11T00:00:00.000Z",
        "createdBy": 13,
        "statusId": 9,
        "order_index": 0,
        "organizationId": 17,
        "author": {
            "firstName": "alena",
            "lastName": "prilipko",
            "id": 13,
            "email": "hwyxlisjb@emlpro.com"
        }
    },
    "admin": true
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

