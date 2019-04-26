# /items

{% api-method method="get" host="http://pm415.com/api/items/:showArchived/:tableName/:orgId/:ownerId" path="" %}
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

{% endapi-method-parameter %}

{% api-method-parameter name="showarchived" type="string" required=true %}

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
    "items": [],
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

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

