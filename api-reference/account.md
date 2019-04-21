---
description: 'These methods allow you to login, get tokens, register, and change passwords.'
---

# /account

{% api-method method="post" host="https://pm415.com" path="/api/account/login" %}
{% api-method-summary %}
Login
{% endapi-method-summary %}

{% api-method-description %}
Retrieves a valid token that can be set as `Bearer` in the authorization header. Alternatively, you can use an API key from your user profile.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="" type="object" required=true %}
`{"email":"mattreider@tmail.com", "password":"reider1"}`
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Login successful
{% endapi-method-response-example-description %}

```javascript
{
    "token": "eyJ4gTkzXw-ayco9GYMxc1r9xDs...etc...",
    "success": true,
    "user": {
        "id": 4,
        "email": "mattreider@tmail.com",
        "firstName": "Matthew",
        "lastName": "Reider",
        "organizations": [
            {
                "id": 6,
                "name": "matt-org"
            }
        ]
    }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Login failed
{% endapi-method-response-example-description %}

```
{
    "statusCode": 400,
    "error": "Bad Request",
    "message": "\"Password\" is required",
    "success": false
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "statusCode": 404,
    "error": "Not Found",
    "message": "User with email mattreider344@tmail.com not found.",
    "success": false
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://pm415.com" path="/api/account/forgotpassword" %}
{% api-method-summary %}
Forgot Password
{% endapi-method-summary %}

{% api-method-description %}
Sends a message to user with a password reminder.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="" type="object" required=true %}
`{"email" : "mattreider@tmail.com"}`
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Message sent
{% endapi-method-response-example-description %}

```
{
    "message": "A message was sent to the mattreider@tmail.com",
    "success": true,
    "userId": 4
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "statusCode": 400,
    "error": "Bad Request",
    "message": "\"Email\" is required",
    "success": false
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "statusCode": 404,
    "error": "Not Found",
    "message": "User with email mattreider44@tmail.com not found.",
    "success": false
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://pm415.com" path="/api/account/register" %}
{% api-method-summary %}
Register \(new org\)
{% endapi-method-summary %}

{% api-method-description %}
Register an account for a new organization.  
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="" type="object" required=true %}
`{"email" : "mattreider@tmail.com",  
 "password": "1111",  
 "confirmation": "1111",  
 "firstName": "Matt",  
 "lastName": "Reider",  
 "tosAccepted": "Y",  
 "organization": "MyOrg"}`
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Registration successful
{% endapi-method-response-example-description %}

```
{
    "userId": 9,
    "success": true
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "statusCode": 400,
    "error": "Bad Request",
    "message": "\"First Name\" is required",
    "success": false
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://pm415.com" path="/api/account/register" %}
{% api-method-summary %}
Register \(existing org\)
{% endapi-method-summary %}

{% api-method-description %}
Registers users to an existing org. Requires the invitation token that was sent to them by the user that registered the org and invited them.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="" type="object" required=true %}
`{"email" : "mattreider@tmail.com", "password": "1111", "confirmation": "1111", "firstName": "Matt", "lastName": "Reider", "tosAccepted": "Y", "token": "934flsdf94rjsdnk92"}`
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "userId": 9,
    "success": true
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "statusCode": 400,
    "error": "Bad Request",
    "message": "\"Token\" is required",
    "success": false
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://pm415.com" path="/api/account/verify?token=eyJiUf3556" %}
{% api-method-summary %}
Verify account
{% endapi-method-summary %}

{% api-method-description %}
Verifies user account using token from verification email.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="token" type="string" required=true %}
**`Token that was sent in the verification email.`**
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Account verified
{% endapi-method-response-example-description %}

```
{
 "userId": 6,
 "success": true,
 "message": "User registration is completed, lets go login"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://pm415.com" path="/api/account/changepassword" %}
{% api-method-summary %}
Change Password
{% endapi-method-summary %}

{% api-method-description %}
Changes password based on forgotten password action, which can only be initiated from a browser. Token must be valid for the request.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="" type="object" required=true %}
`{"password" : "1111",  
"confirmation": "1111",  
"token" : "eyJhbGciOiJIUzIY45gBT7TkTbQ"}`
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Password changed
{% endapi-method-response-example-description %}

```
{
"userId": 4,
"success": true,
"message": "New password saved"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

