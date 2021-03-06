---
description: 'These methods allow you to create, edit, delete and get info on bugs.'
---

# /bugs

{% api-method method="post" host="https://pm415.com" path="/api/bugs/new/:orgid" %}
{% api-method-summary %}
Create new bug
{% endapi-method-summary %}

{% api-method-description %}
Creates a new bug.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name=":orgid" type="number" required=true %}
The ID of the org
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
Authorization: Bearer 50ca9ba0f7b1444fa55d5
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="" type="object" required=true %}
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

{% api-method method="get" host="https://pm415.com" path="/api/bugs/full/:showarchived/:orgid/:fullselect" %}
{% api-method-summary %}
Get bug list
{% endapi-method-summary %}

{% api-method-description %}
Gets the list of bugs
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name=":fullselect" type="boolean" required=true %}
True or false
{% endapi-method-parameter %}

{% api-method-parameter name=":orgid" type="number" required=true %}
The ID of the org
{% endapi-method-parameter %}

{% api-method-parameter name=":showarchived" type="boolean" required=true %}
True or false
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

{% api-method method="get" host="https://pm415.com" path="/api/bugs/:orgid/:bugid" %}
{% api-method-summary %}
Get info on current bug
{% endapi-method-summary %}

{% api-method-description %}
Gets the information on the current bug.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name=":bugid" type="number" required=true %}
The ID of the bug you want to work with
{% endapi-method-parameter %}

{% api-method-parameter name=":orgid" type="number" required=true %}
The ID of the org
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
    "bug": {
        "createdAt": "2019-04-27T09:41:44.000Z",
        "assignee": {
            "firstName": "alena",
            "lastName": "prilipko",
            "id": 13,
            "email": "hwyxlisjb@emlpro.com"
        },
        "archived": 0,
        "id": 5,
        "title": "kjggkjkb",
        "description": "jhgjhg",
        "statusId": 14,
        "createdBy": 13,
        "reportedBy": {
            "firstName": "alena",
            "lastName": "prilipko",
            "id": 13,
            "email": "hwyxlisjb@emlpro.com"
        },
        "severity": "P2"
    },
    "admin": true
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://pm415.com" path="/api/bugs/:orgid" %}
{% api-method-summary %}
Get list of selected bugs
{% endapi-method-summary %}

{% api-method-description %}
Gets the list of selected bugs.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name=":orgid" type="number" required=true %}
The ID of the org
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
Authorization: Bearer 50ca9ba0f7b1444fa55d5
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="" type="object" required=true %}
{"bugId": \["5"\], "fullSelect": true}
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
            "severity": "P2"
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="put" host="https://pm415.com" path="/api/bugs/edit/:orgid/:bugid" %}
{% api-method-summary %}
Update current bug
{% endapi-method-summary %}

{% api-method-description %}
Updates the current bug.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name=":bugid" type="number" required=true %}
The ID of the bug you want to update
{% endapi-method-parameter %}

{% api-method-parameter name=":orgid" type="number" required=true %}
The ID of the org
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
Authorization: Bearer 50ca9ba0f7b1444fa55d5
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="" type="object" required=true %}
{"title": "aasdsadasdasdasdasd3", "statusId": "16"}
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
    "bug": {
        "id": 5,
        "assignee": 13,
        "organizationId": 17,
        "mailers": "!hwyxlisjb@emlpro.com!",
        "title": "aasdsadasdasdasdasd3",
        "description": "jhgjhg",
        "statusId": "16",
        "severity": "P2",
        "createdAt": "2019-04-27T09:41:44.000Z",
        "createdBy": 13,
        "reportedBy": null,
        "updatedAt": "2019-04-27T09:41:44.000Z",
        "archived": 0,
        "updated_at": "2019-04-27T11:38:19.285Z"
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="delete" host="https://pm415.com" path="/api/bugs/:ogrid/:bugid" %}
{% api-method-summary %}
Delete bug
{% endapi-method-summary %}

{% api-method-description %}
Deletes the bug.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name=":bugid" type="number" required=true %}
The ID of the bug you want to delete
{% endapi-method-parameter %}

{% api-method-parameter name=":orgid" type="number" required=true %}
The ID of the org
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
    "bug": 5,
    "message": "bug deleted"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

