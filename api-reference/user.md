---
description: >-
  Some user methods are located beneath the Org endpoint. Others are under
  /users
---

# /user

{% api-method method="get" host="https://pm415.com" path="/api/user" %}
{% api-method-summary %}
Get current user
{% endapi-method-summary %}

{% api-method-description %}
Gets info about the current user
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
`Authorization: Bearer 50ca9ba0f7b1444fa55d5`
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
User retrieved
{% endapi-method-response-example-description %}

```javascript
{
    "success": true,
    "user": {
        "id": 4,
        "email": "mattreider@tmnail.com",
        "firstName": "Matthew",
        "lastName": "Reider",
        "organizations": [
            {
                "id": 16,
                "name": "Bar",
                "roles": [
                    {
                        "id": 1,
                        "role": "Admin"
                    }
                ]
            }
        ]
    },
    "organization": {
        "id": 16,
        "name": "Bar",
        "roles": [
            {
                "id": 1,
                "role": "Admin"
            }
        ]
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="put" host="https://pm415.com" path="/api/user" %}
{% api-method-summary %}
Update current user
{% endapi-method-summary %}

{% api-method-description %}
Updates the current user
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
`Authorization: Bearer 50ca9ba0f7b1444fa55d5`
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="" type="string" required=true %}
`{"email" : "matt@matt.com", "password": "1111", "confirmation": "1111", "firstName": "Matt", "lastName": "Reider" }`
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
User retrieved
{% endapi-method-response-example-description %}

```javascript
{
    "success": true,
    "user": {
        "id": 4,
        "email": "mattreider@tmnail.com",
        "firstName": "Matthew",
        "lastName": "Reider",
        "organizations": [
            {
                "id": 16,
                "name": "Bar",
                "roles": [
                    {
                        "id": 1,
                        "role": "Admin"
                    }
                ]
            }
        ]
    },
    "organization": {
        "id": 16,
        "name": "Bar",
        "roles": [
            {
                "id": 1,
                "role": "Admin"
            }
        ]
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

