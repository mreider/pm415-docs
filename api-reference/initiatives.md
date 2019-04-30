# /initiatives

{% api-method method="get" host="https://pm415.com" path="/api/initiatives/all/:showarchived/:orgid" %}
{% api-method-summary %}
Get initiatives list
{% endapi-method-summary %}

{% api-method-description %}
Gets the initiatives list.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
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

{% api-method method="get" host="https://pm415.com" path="/api/initiatives/:orgid/:initiativeid" %}
{% api-method-summary %}
Get current initiative
{% endapi-method-summary %}

{% api-method-description %}
Gets the current initiative information.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name=":initiativeid" type="number" required=true %}
The ID of the initiative
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

{% api-method method="post" host="https://pm415.com" path="/api/initiatives/:orgid" %}
{% api-method-summary %}
Get info on selected initiatives
{% endapi-method-summary %}

{% api-method-description %}
Gets the information on  the selected initiatives.
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
{"initiativeId": \["25"\], "fullSelect": true}
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
    "initiatives": [
        {
            "createdAt": "2019-04-27T07:05:58.000Z",
            "id": 25,
            "title": "Api created",
            "archived": 0,
            "description": "api created Description",
            "horizon": "2011-11-11T00:00:00.000Z",
            "createdBy": 13,
            "statusId": 9,
            "orderIndex": 0,
            "organizationId": 17
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://pm415.com" path="/api/initiatives/new/:orgid  " %}
{% api-method-summary %}
Create new initiative
{% endapi-method-summary %}

{% api-method-description %}
Creates the new initiative.
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
{"title": "Api created", "description": "api created Description", "statusId":"9", "horizon":"111111"}
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
    "initiative": {
        "title": "Api created",
        "description": "api created Description",
        "statusId": "9",
        "horizon": "111111",
        "organization_id": 17,
        "created_by": 13,
        "updated_at": "2019-04-27T07:44:48.165Z",
        "created_at": "2019-04-27T07:44:48.165Z",
        "id": 26
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="put" host="https://pm415.com" path="/api/initiatives/edit/:orgid/:initiativeid" %}
{% api-method-summary %}
Update current initiative
{% endapi-method-summary %}

{% api-method-description %}
Updates the current initiative
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name=":initiativeid" type="number" required=true %}
The ID of the initiative you want to update
{% endapi-method-parameter %}

{% api-method-parameter name=":orgid" type="number" required=true %}
The ID of the org
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication " type="string" required=true %}
Authorization: Bearer 50ca9ba0f7b1444fa55d5
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="" type="object" required=true %}
{"title": "aasdsadasdasdasdasd3", "statusId": "10"}
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
    "initiative": {
        "id": 26,
        "title": "aasdsadasdasdasdasd3",
        "description": "api created Description",
        "horizon": "2011-11-11T00:00:00.000Z",
        "statusId": "10",
        "createdBy": 13,
        "createdAt": "2019-04-27T07:44:48.000Z",
        "updatedAt": "2019-04-27T07:57:43.000Z",
        "organizationId": 17,
        "mailers": null,
        "archived": 0,
        "orderIndex": 0,
        "updated_at": "2019-04-27T07:58:37.620Z"
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="delete" host="https://pm415.com" path="/api/initiatives/:orgid/:initiativeid" %}
{% api-method-summary %}
Delete initiative
{% endapi-method-summary %}

{% api-method-description %}
Deletes the initiative.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name=":initiativeid" type="number" required=true %}
The ID of the initiative you want to delete
{% endapi-method-parameter %}

{% api-method-parameter name=":orgid" type="number" required=true %}
The ID of the org
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
    "initiative": 26,
    "message": "initiative deleted"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

