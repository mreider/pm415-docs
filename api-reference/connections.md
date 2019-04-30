---
description: >-
  These methods allow you to create and get info on connections between items,
  bugs and initiatives.
---

# /connections

{% api-method method="post" host="https://pm415.com" path="/api/connections/:ownertable/:id" %}
{% api-method-summary %}
Create connection
{% endapi-method-summary %}

{% api-method-description %}
Creates the connection between items, bugs, iniatives.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name=":id" type="number" required=true %}
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
{"items": \[\], "initiatives": \[28\], "bugs": \[\], "backlogs": \[\], "delete": false}
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

{% api-method method="get" host="https://pm415.com" path="/api/connections/:needinfotable/:infotable/:id" %}
{% api-method-summary %}
Get connections list
{% endapi-method-summary %}

{% api-method-description %}
Gets the list of connections.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name=":id" type="number" required=true %}
The ID of the bug or initiative or item
{% endapi-method-parameter %}

{% api-method-parameter name=":infotable" type="string" required=true %}
"Bugs" or "Initiatives" or "Items"
{% endapi-method-parameter %}

{% api-method-parameter name=":needinfotable" type="string" required=true %}
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
    "connections": [
        {
            "id": 7,
            "initiativeId": 28,
            "backlogId": null,
            "itemId": null,
            "bugId": 6
        },
        {
            "id": 8,
            "initiativeId": null,
            "backlogId": null,
            "itemId": 52,
            "bugId": 6
        }
    ],
    "info": [
        {
            "assignee": null,
            "organizationId": 17,
            "id": 52,
            "title": "abc",
            "description": "Description",
            "statusId": 3,
            "points": 0,
            "createdBy": 13,
            "forecastedRelease": null,
            "actualRelease": null,
            "plannedOn": null,
            "ownerId": 19,
            "ownerTable": "backlogs",
            "mailers": "!hwyxlisjb@emlpro.com!",
            "orderIndex": 2,
            "archived": 0
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

