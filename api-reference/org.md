---
description: >-
  These methods allow you to create, delete and switch orgs. Other org methods
  allow you to invite and remove users from orgs.
---

# /org

{% api-method method="post" host="https://pm415.com" path="/api/org" %}
{% api-method-summary %}
Create an org
{% endapi-method-summary %}

{% api-method-description %}
Creates an organization.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
`Authorization: Bearer 50ca9ba0f7b1444fa55d5`
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="" type="object" required=true %}
`{"name" : "myOrg"}`
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```javascript
{
    "success": true,
    "organization": {
        "name": "myOrg",
        "updated_at": "2019-04-20T19:22:13.740Z",
        "created_at": "2019-04-20T19:22:13.740Z",
        "id": 15
    },
    "user": {
        "id": 4,
        "email": "mattreider@tmail.com",
        "password": "f115e42cc1a509ed5a03879574e71",
        "firstName": "Matthew",
        "lastName": "Reider",
        "isActive": 1,
        "confirmedAt": "2019-04-08T02:38:54.000Z",
        "createdAt": "2019-04-08T02:38:34.000Z",
        "updatedAt": "2019-04-08T02:38:54.000Z",
        "apiKey": "50ca9ba0f7b14f1932a1f81",
        "organizations": [
            {
                "id": 6,
                "name": "foo",
                "createdAt": "2019-04-08T02:38:34.000Z",
                "updatedAt": "2019-04-08T02:38:34.000Z",
                "roles": [
                    {
                        "id": 1,
                        "role": "Admin",
                        "createdAt": "2019-04-08T02:30:37.000Z",
                        "updatedAt": "2019-04-08T02:30:37.000Z"
                    }
                ]
            }
        ]
    }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Could not find a cake matching this query.
{% endapi-method-response-example-description %}

```javascript
{
    "statusCode": 400,
    "error": "Bad Request",
    "message": "\"Name\" is required",
    "success": false
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://pm415.com" path="/api/org" %}
{% api-method-summary %}
Get org info
{% endapi-method-summary %}

{% api-method-description %}
Gets info about all of the orgs. There are no request parameters - only a response.
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

{% endapi-method-response-example-description %}

```text
{
    "success": true,
    "organizations": [
        {
            "id": 6,
            "name": "foo",
            "createdAt": "2019-04-08T02:38:34.000Z",
            "updatedAt": "2019-04-08T02:38:34.000Z",
            "roles": [
                {
                    "id": 1,
                    "role": "Admin",
                    "createdAt": "2019-04-08T02:30:37.000Z",
                    "updatedAt": "2019-04-08T02:30:37.000Z"
                }
            ]
        },
        {
            "id": 15,
            "name": "myOrg",
            "createdAt": "2019-04-20T19:22:13.000Z",
            "updatedAt": "2019-04-20T19:22:13.000Z",
            "roles": [
                {
                    "id": 1,
                    "role": "Admin",
                    "createdAt": "2019-04-08T02:30:37.000Z",
                    "updatedAt": "2019-04-08T02:30:37.000Z"
                }
            ]
        }
    ],
    "current": {
        "id": 6,
        "name": "foo",
        "createdAt": "2019-04-08T02:38:34.000Z",
        "updatedAt": "2019-04-08T02:38:34.000Z",
        "roles": [
            {
                "id": 1,
                "role": "Admin",
                "createdAt": "2019-04-08T02:30:37.000Z",
                "updatedAt": "2019-04-08T02:30:37.000Z"
            }
        ]
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://pm415.com" path="/api/org/switch/:orgid" %}
{% api-method-summary %}
Switch orgs
{% endapi-method-summary %}

{% api-method-description %}
Switches orgs and generates a new token. This is useful if you are building a user interface, or CLI tool, and want to operate on one org at a time. The org you operate on is encapsulated in the token. Switching orgs, and tokens, allows you to operate on different orgs without having to save sessions artifacts \(cookies, web storage, files, etc\) on the client.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name=":orgid" type="number" required=true %}
ID of the org you want to switch to
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
`Authorization: Bearer 50ca9ba0f7b1444fa55d5`
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Switched orgs
{% endapi-method-response-example-description %}

```text
{
    "success": true,
    "organization": 1,
    "token": "00jf9w4dog73jfosdfu"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="put" host="https://pm415.com" path="/api/org/:orgid" %}
{% api-method-summary %}
Update an org
{% endapi-method-summary %}

{% api-method-description %}
Update an org's name
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name=":orgid" type="number" required=true %}
ID of the org you want to update
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
`Authorization: Bearer 50ca9ba0f7b1444fa55d5`
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="" type="object" required=true %}
`{"name": "updatedOrgName"}`
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
`{    
"success": true,    
"organization": 6    
}`
{% endapi-method-response-example-description %}

```text

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="delete" host="https://pm415.com" path="/api/org/:orgid" %}
{% api-method-summary %}
Delete an org
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name=":orgid" type="number" required=true %}
The ID of the org you want to delete
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
`Authorization: Bearer 50ca9ba0f7b1444fa55d5`
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
    "success": true
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://pm415.com" path="/api/org/:orgid/users" %}
{% api-method-summary %}
Get users
{% endapi-method-summary %}

{% api-method-description %}
Gets information about an organization's users
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name=":orgid" type="string" required=true %}
ID of the org you want to query
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
`Authorization: Bearer 50ca9ba0f7b1444fa55d5`
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
    "success": true,
    "users": [
        {
            "userId": 4,
            "email": "mattr@tmail.com",
            "firstName": "Matthew",
            "lastName": "Reider",
            "isActive": 1,
            "role": "Admin"
        },
        {
            "userId": 6,
            "email": "suziereider@tmail.com",
            "firstName": "Suzie",
            "lastName": "Reider",
            "isActive": 1,
            "role": "Admin"
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://pm415.com" path="/api/org/invite/?token=8s80f934kf94" %}
{% api-method-summary %}
Validate an user invite token
{% endapi-method-summary %}

{% api-method-description %}
Checks an invite token to see if it is valid and who it belongs to._This method is used by the PM415 user interface and may not have any other practical use case._
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
`Authorization: Bearer 50ca9ba0f7b1444fa55d5`
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="token" type="string" required=true %}
Invitation token sent to a user.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
    success: true,
    "email": "mattreider@tmail.com",
    "organization": "my-org"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://pm415.com" path="/api/org/:orgid/invitelink" %}
{% api-method-summary %}
Generate an invite link
{% endapi-method-summary %}

{% api-method-description %}
Creates an invite link for a new user.
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
`{email: “suziereider@tmail.com”}`
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
   "success": true,
   "confirmUrl": "https://pm415.com/account/invite/?token=eyJh
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://pm415.com/" path="/api/org/:orgid/users/remove" %}
{% api-method-summary %}
Remove users
{% endapi-method-summary %}

{% api-method-description %}
Removes users from an organization. This does not delete the user's profile - just the link between the org and the user. To add them back, you must re-invite them.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name=":orgid" type="string" required=true %}
The ID of the org you want to work with
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
`Authorization: Bearer 50ca9ba0f7b1444fa55d5`
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="" type="object" required=true %}
`{"usersId": ["4", "6"]}`
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
   "success": true
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="put" host="https://pm415.com" path="/api/org/:orgid/admin/grant" %}
{% api-method-summary %}
Grant admin
{% endapi-method-summary %}

{% api-method-description %}
Gives a user admin privileges. Admins can perform all operations on an org and its users.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name=":orgid" type="string" required=true %}
The ID of the org you want to work with
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
`Authorization: Bearer 50ca9ba0f7b1444fa55d5`
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="" type="object" required=true %}
`{"usersId": ["4", "6"]}`
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
   "success": true
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="put" host="https://pm415.com" path="/api/org/:orgid/admin/revoke" %}
{% api-method-summary %}
Revoke admin
{% endapi-method-summary %}

{% api-method-description %}
Revokes a user's admin privileges.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name=":orgid" type="string" required=true %}
The ID of the org you want to work with
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
`Authorization: Bearer 50ca9ba0f7b1444fa55d5`
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="" type="object" required=true %}
`{"usersId": ["4", "6"]}`
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
   "success": true
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="put" host="https://pm415.com" path="/api/org/:orgid/admin/resetpassword" %}
{% api-method-summary %}
Reset password
{% endapi-method-summary %}

{% api-method-description %}
Resets user passwords and sends emails with reset links.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name=":orgid" type="string" required=true %}
The ID of the org you want to work with
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
`Authorization: Bearer 50ca9ba0f7b1444fa55d5`
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="" type="object" required=true %}
`{"usersId": ["4", "6"]}`
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
   "success": true
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

