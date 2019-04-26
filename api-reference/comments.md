# /comments

{% api-method method="post" host="http://pm415.com:3000/api/comments/new/tablename/:orgid/:ownerid" path="" %}
{% api-method-summary %}
Create a comment
{% endapi-method-summary %}

{% api-method-description %}
Creates the new comment 
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="ownerid" type="number" required=true %}

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
    "comment": {
        "comment": "comment2-2",
        "organization_id": 17,
        "created_by": 13,
        "ownerId": 49,
        "ownerTable": "items",
        "mailers": "",
        "updated_at": "2019-04-26T08:34:57.752Z",
        "created_at": "2019-04-26T08:34:57.752Z",
        "id": 54
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="http://pm415.com:3000/api/comments/get/:ownerTable/:orgId/:ownerId" path="" %}
{% api-method-summary %}
Get list of comments
{% endapi-method-summary %}

{% api-method-description %}
Gets the list of comments
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="ownerid" type="number" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="orgid" type="number" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="ownertable" type="string" required=true %}
name of table parent comment
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
    "comments": [
        {
            "id": 48,
            "ownerId": 49,
            "ownerTable": "items",
            "mailers": "",
            "comment": "comment1",
            "createdAt": "2019-04-26T07:13:39.000Z",
            "createdBy": 13,
            "updatedAt": "2019-04-26T08:31:59.000Z",
            "organizationId": 17
        },
        {
            "id": 51,
            "ownerId": 49,
            "ownerTable": "items",
            "mailers": "",
            "comment": "comment2-1",
            "createdAt": "2019-04-26T07:48:19.000Z",
            "createdBy": 13,
            "updatedAt": "2019-04-26T08:32:27.000Z",
            "organizationId": 17
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="put" host="http://pm415.com:3000/api/comments/edit/:commentId" path="" %}
{% api-method-summary %}
Update current backlog
{% endapi-method-summary %}

{% api-method-description %}
Updates the current backlog
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="commentid" type="number" required=true %}

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
    "comment": {
        "id": 52,
        "ownerId": 49,
        "ownerTable": "items",
        "mailers": "",
        "comment": "commentUpdated",
        "createdAt": "2019-04-26T08:33:39.000Z",
        "createdBy": 13,
        "updatedAt": "2019-04-26T08:33:39.000Z",
        "organizationId": 17,
        "updated_at": "2019-04-26T08:37:59.009Z"
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="delete" host="http://localhost:3000/api/comments/delete/:orgId/:commentId" path="" %}
{% api-method-summary %}
Delete a comment
{% endapi-method-summary %}

{% api-method-description %}
Delets the chosen comment
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="commentid" type="number" required=true %}

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
    "comment": 49,
    "message": "Comment deleted"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

