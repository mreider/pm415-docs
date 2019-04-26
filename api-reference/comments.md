# /comments

{% api-method method="post" host="http://pm415.com:3000/api/comments/new/tablename/:orgid/:ownerid" path="" %}
{% api-method-summary %}
Create a comment
{% endapi-method-summary %}

{% api-method-description %}
Creates the comment 
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
        "comment": "fgbdtn",
        "organization_id": 17,
        "created_by": 13,
        "ownerId": 49,
        "ownerTable": "items",
        "mailers": "",
        "updated_at": "2019-04-26T07:32:42.216Z",
        "created_at": "2019-04-26T07:32:42.216Z",
        "id": 49
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

