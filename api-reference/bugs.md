# /bugs

{% api-method method="post" host="http://pm415.com:3000/api/bugs/new/:orgId" path="" %}
{% api-method-summary %}
Create new bag
{% endapi-method-summary %}

{% api-method-description %}
Creates new bag
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="orgid" type="number" required=true %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
Authorization: Bearer 50ca9ba0f7b1444fa55d5
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="" type="string" required=true %}
{"title": "Api created", "description": "api created Description", "statusId":"14", "createdBy": "1"}
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
"success": true,
"bugs":{
"title": "Api created",
"description": "api created Description",
"statusId": "14",
"createdBy": "1",
"organizationId": 1,
"mailers": "!nosuchip@gmail.com!",
"updated_at": "2019-04-27T09:38:47.554Z",
"created_at": "2019-04-27T09:38:47.554Z",
"id": 37
}
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="http://pm415.com:3000/api/bugs/full/:showarchived/:orgId/:fullSelect" path="" %}
{% api-method-summary %}
Get bug list
{% endapi-method-summary %}

{% api-method-description %}
Gets the list of bugs
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="fullselect" type="boolean" required=true %}
true or false
{% endapi-method-parameter %}

{% api-method-parameter name="orgid" type="number" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="showarchived" type="boolean" required=true %}
true or false
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
    "bugs": [
        {
            "createdAt": "2019-04-27T09:41:44.000Z",
            "assignee": 13,
            "archived": 0,
            "id": 5,
            "title": "kjggkjkb",
            "description": "jhgjhg",
            "statusId": 14,
            "createdBy": 13,
            "reportedBy": null,
            "severity": "P2",
            "reportedByData": {
                "email": "hwyxlisjb@emlpro.com",
                "firstName": "alena",
                "lastName": "prilipko"
            },
            "assigneeData": {
                "email": "hwyxlisjb@emlpro.com",
                "firstName": "alena",
                "lastName": "prilipko"
            },
            "items": [],
            "initiatives": [],
            "comments": []
        }
    ],
    "admin": true
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

