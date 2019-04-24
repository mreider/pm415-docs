# /backlogs

{% api-method method="get" host="http://pm415:3000/api/backlogs/:showArchived/:orgId" path="" %}
{% api-method-summary %}
Get list of backlogs
{% endapi-method-summary %}

{% api-method-description %}
Shows the list of backlogs
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="orgID" type="number" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="showArchived" type="boolean" required=true %}

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
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```javascript
{
    "success": true,
    "backlogs": [
        {
            "email": "hwyxlisjb@emlpro.com",
            "firstName": "alena",
            "lastName": "prilipko",
            "id": 17,
            "title": "hhhh",
            "description": null,
            "archived": 0,
            "statusId": 1,
            "createdBy": 13
        }
    ],
    "admin": true
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



