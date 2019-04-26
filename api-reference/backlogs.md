# /backlogs

{% api-method method="get" host="http://pm415.com/api/backlogs/:showarchived/:orgid" path="" %}
{% api-method-summary %}
Get list of backlogs
{% endapi-method-summary %}

{% api-method-description %}
Shows the list of backlogs
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="orgid" type="number" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="showarchived" type="boolean" required=true %}

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
Backlogs retrieved
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

{% api-method method="post" host="http://pm415.com:3000/api/backlogs/:orgid" path="" %}
{% api-method-summary %}
Select full data of backlogs
{% endapi-method-summary %}

{% api-method-description %}
Selects the full data of backlogs
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="orgId" type="number" required=true %}
 
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
 Authorization: Bearer 50ca9ba0f7b1444fa55d5
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="" type="string" required=true %}
{"backlogsId": \["17","2"\], "fullSelect": true}
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
    "backlogs": [
        {
            "createdAt": "2019-04-24T07:43:40.000Z",
            "points": 0,
            "assignee": null,
            "archived": 0,
            "id": 17,
            "title": "hhhh",
            "description": null,
            "statusId": 1,
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

{% api-method method="put" host="http://pm415.com:3000/api/backlogs/edit/:orgid/:backlogid" path="" %}
{% api-method-summary %}
Update current backlog
{% endapi-method-summary %}

{% api-method-description %}
Updates the current backlog
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="orgid" type="number" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="backlogid" type="number" required=true %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
Authorization: Bearer 50ca9ba0f7b1444fa55d5
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="" type="string" required=true %}
{"title": "mmm", "statusId": "2" }
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
    "backlog": {
        "assignee": null,
        "organizationId": 17,
        "id": 18,
        "title": "mmm",
        "description": null,
        "statusId": "2",
        "points": 0,
        "createdAt": "2019-04-24T10:46:34.000Z",
        "createdBy": 13,
        "updatedAt": "2019-04-24T10:49:47.000Z",
        "forecastedRelease": null,
        "actualRelease": null,
        "plannedOn": "2019-04-24T10:49:47.000Z",
        "archived": 0,
        "updated_at": "2019-04-24T14:45:38.899Z"
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="http://pm415.com:3000/api/backlogs/new/:orgid" path="" %}
{% api-method-summary %}
Create new backlog
{% endapi-method-summary %}

{% api-method-description %}
Creates a new backlog for the current organization
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
{"title": "asdasd", "statusId": "2"}
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
    "backlog": {
        "title": "asdasd",
        "statusId": "2",
        "organization_id": 17,
        "created_by": 13,
        "plannedOn": "2019-04-24T15:10:13.229Z",
        "updated_at": "2019-04-24T15:10:13.229Z",
        "created_at": "2019-04-24T15:10:13.229Z",
        "id": 19
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="delete" host="http://pm415.com:3000/api/backlogs/:orgid/:backlogid" path="" %}
{% api-method-summary %}
Delete a backlog
{% endapi-method-summary %}

{% api-method-description %}
Deletes the chosen backlog
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="" type="number" required=true %}
backlogid
{% endapi-method-parameter %}

{% api-method-parameter name="" type="number" required=true %}
orgid
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
    "backlog": 18,
    "message": "Backlog deleted"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

