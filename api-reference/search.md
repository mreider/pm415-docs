# /search

{% api-method method="get" host="https://pm415.com" path="/api/search/:query/:orgid/:showarchived" %}
{% api-method-summary %}
Get information on a request
{% endapi-method-summary %}

{% api-method-description %}
Gets the information on a text string request.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name=":showarchived" type="boolean" required=true %}
True or false
{% endapi-method-parameter %}

{% api-method-parameter name=":orgid" type="number" required=true %}
The ID of the org
{% endapi-method-parameter %}

{% api-method-parameter name=":query" type="string" required=true %}
Your text string request
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
    "data": [
        {
            "title": "Api created",
            "description": "api created Description",
            "type": "initiatives",
            "author": {
                "id": 13,
                "email": "hwyxlisjb@emlpro.com",
                "firstName": "alena",
                "lastName": "prilipko"
            },
            "assignee": {},
            "organization": 17,
            "id": 25,
            "createdOn": "2019-04-27T07:05:58.621Z",
            "ownerId": "",
            "archived": 0
        }
    ],
    "query": {
        "query": {
            "bool": {
                "must": [
                    {
                        "multi_match": {
                            "query": "api",
                            "fields": [
                                "title",
                                "description",
                                "comment",
                                "author.firstName",
                                "author.lastName",
                                "author.email",
                                "assignee.firstName",
                                "assignee.lastName",
                                "assignee.email",
                                "ownerTable"
                            ],
                            "type": "phrase_prefix"
                        }
                    },
                    {
                        "match": {
                            "organization": "17"
                        }
                    }
                ]
            }
        }
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://pm415.com" path="/api/search/reindex" %}
{% api-method-summary %}
Add all data
{% endapi-method-summary %}

{% api-method-description %}
Adds all data from database into elastic index.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
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
    "indexInitiatives": true,
    "indexItems": true,
    "indexBacklogs": true,
    "indexBugs": true,
    "indexComments": true
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

