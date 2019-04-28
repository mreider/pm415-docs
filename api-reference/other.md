# /other

{% api-method method="put" host="http://pm415.com:3000/api/orderindexchange/:orgId" path="" %}
{% api-method-summary %}
Change sorting order for initiatives or items
{% endapi-method-summary %}

{% api-method-description %}
Changes the sorting order for array of initiatives or items
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
{"items": \["50","51", "52", "53", "54", "55"\], "initiatives": \[\]}
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

