# /items

{% api-method method="get" host="http://pm415.com" path="/api/items/:showArchived/:tableName/:orgId/:ownerId" %}
{% api-method-summary %}
Get list of items
{% endapi-method-summary %}

{% api-method-description %}
Gets the list of items
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="ownerid" type="number" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="orgid" type="number" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="tablename" type="string" required=true %}
owner table of item \(backlogs\)
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
    "items": [
        {
            "email": "hwyxlisjb@emlpro.com",
            "firstName": "alena",
            "lastName": "prilipko",
            "id": 50,
            "title": "hhhh",
            "statusId": 1,
            "archived": 0,
            "createdBy": 13,
            "ownerId": 19,
            "order_index": 0
        },
        {
            "email": "hwyxlisjb@emlpro.com",
            "firstName": "alena",
            "lastName": "prilipko",
            "id": 51,
            "title": "abc",
            "statusId": 1,
            "archived": 0,
            "createdBy": 13,
            "ownerId": 19,
            "order_index": 0
        },
        {
            "email": "hwyxlisjb@emlpro.com",
            "firstName": "alena",
            "lastName": "prilipko",
            "id": 52,
            "title": "abc",
            "statusId": 3,
            "archived": 0,
            "createdBy": 13,
            "ownerId": 19,
            "order_index": 2
        }
    ],
    "admin": true
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="http://pm415.com:3000/api/items/new/:orgid" path="" %}
{% api-method-summary %}
Create new item
{% endapi-method-summary %}

{% api-method-description %}
Creates the item
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="orgid" type="number" required=true %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=false %}
Authorization: Bearer 50ca9ba0f7b1444fa55d5
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="" type="string" required=true %}
{"ownerTable": "backlogs", "ownerId": "19", "title": "abc", "description": "Description"}
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
    "item": {
        "ownerTable": "backlogs",
        "ownerId": "19",
        "title": "abc",
        "description": "Description",
        "organization_id": 17,
        "created_by": 13,
        "mailers": "!hwyxlisjb@emlpro.com!",
        "updated_at": "2019-04-26T12:31:28.581Z",
        "created_at": "2019-04-26T12:31:28.581Z",
        "id": 51
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="http://pm415.com/api/items/:orgId/:itemId" path="" %}
{% api-method-summary %}
Get current item
{% endapi-method-summary %}

{% api-method-description %}
Gets the information about the current item
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="itemid" type="number" required=true %}

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
    "item": {
        "createdAt": "2019-04-26T12:31:28.000Z",
        "archived": 0,
        "ownerId": 19,
        "points": 0,
        "assignee": {
            "firstName": "",
            "lastName": "",
            "email": "",
            "id": 0
        },
        "id": 51,
        "title": "abc",
        "description": "Description",
        "statusId": 1,
        "order_index": 0,
        "createdBy": 13,
        "forecastedRelease": null,
        "actualRelease": null,
        "plannedOn": null,
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

{% api-method method="put" host="http://pm415.com/api/items/edit/:orgId/:itemId" path="" %}
{% api-method-summary %}
Updates current item
{% endapi-method-summary %}

{% api-method-description %}
Updates the current item
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="itemid" type="number" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="orgid" type="number" required=true %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
Authorization: Bearer 50ca9ba0f7b1444fa55d5
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="" type="string" required=false %}
{"statusId": "3", "order\_index": "2"} or any field of item
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
    "item": {
        "assignee": null,
        "organizationId": 17,
        "id": 52,
        "title": "abc",
        "description": "Description",
        "statusId": "3",
        "points": 0,
        "createdAt": "2019-04-26T13:11:13.000Z",
        "createdBy": 13,
        "updatedAt": "2019-04-26T13:11:13.000Z",
        "forecastedRelease": null,
        "actualRelease": null,
        "plannedOn": null,
        "ownerId": 19,
        "ownerTable": "backlogs",
        "mailers": "!hwyxlisjb@emlpro.com!",
        "orderIndex": 0,
        "archived": 0,
        "order_index": "2",
        "updated_at": "2019-04-26T13:34:25.182Z"
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="delete" host="http://pm415.com:3000/api/items/:orgId/:itemId" path="" %}
{% api-method-summary %}
Delete item
{% endapi-method-summary %}

{% api-method-description %}
Deletes the current item
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="itemid" type="number" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="orgid" type="number" required=true %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="" type="string" required=true %}
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
    "backlog": 49,
    "message": "Item deleted"   
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="http://pm415.com/api/items/:orgId" path="" %}
{% api-method-summary %}
Get info on selected items
{% endapi-method-summary %}

{% api-method-description %}
Gets the information on the selected items
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
{"itemsId": \["52","53"\], "fullSelect": true}
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
    "items": [
        {
            "createdAt": "2019-04-26T13:11:13.000Z",
            "archived": 0,
            "ownerId": 19,
            "points": 0,
            "assignee": null,
            "id": 52,
            "title": "abc",
            "description": "Description",
            "statusId": 3,
            "orderIndex": 2,
            "createdBy": 13,
            "forecastedRelease": null,
            "actualRelease": null,
            "plannedOn": null
        },
        {
            "createdAt": "2019-04-27T06:28:47.000Z",
            "archived": 0,
            "ownerId": 19,
            "points": 0,
            "assignee": null,
            "id": 53,
            "title": "abc",
            "description": "Description",
            "statusId": 1,
            "orderIndex": 0,
            "createdBy": 13,
            "forecastedRelease": null,
            "actualRelease": null,
            "plannedOn": null
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

