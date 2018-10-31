---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - javascript
  - json

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - endpoints

search: true
---

# Introduction

Welcome to the TradeFinex API! You can use our API to access TradeFinex API endpoints, which is Trade and Finance Platform.

We have language bindings in Shell, Javascript, and Json! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [TradeFinex](https://tradefinex.org). Feel free to edit it and use it as a base for your own API's documentation.

<aside class="warning">
Please note that this is a beta version of the TradeFinex API which is still undergoing final testing before its official release. 
</aside>


# Authentication

TradeFinex uses API key to allow access to the API. You can request a new  API key at our [developer portal]().

Two ways to authenticate : <br>
		1) JWT Token - issued after using API <br>
    2) API Key based
		
The API Key and JWT Token needs to be included in the request body or as GET param during API call. 

` apiKey: '04af606c-38a3-11e8-b467-0ed5f89f718b' ` <br>
` token: '......jwt token.... ' `

<aside class="notice">
JWT Tokens are set to expire in 24 hours after they are issued.
</aside>

<aside class="notice">
You must replace <code>04af606c-38a3-11e8-b467-0ed5f89f718b</code> with your personal API key.
</aside>

<aside class="success">
There are few endpoints that does not need API key to be included in request.
</aside>
# API Interaction

## Status codes

+ <code>200 OK</code>  Successful request
+ <code>400 Bad Request</code> Validation error
+ <code>401 Unauthorized</code> Invalid API Key
+ <code>404 Not Found</code> The specified resource does not exist
+ <code>500 Internal Server Error</code> Something went wrong

## Response format

Depending on whether the request is successful or not the response format will change.

Endpoint specific data will exist in data object on successful request.

> Successful repsonse format

```json
{
  "status" : "success",
  "data" : {}
}
```

> Failed repsonse format

```json
{
  "status" : "failed",
  "appErrorCode": "",
  "errMessage": ""
}
```

## Errors

List of api errors and their mapping with <code>http</code> status code.

Error Code | Status code | Error Message
--------- | ----------- | -------------
1001 | 400 | The request was unacceptable, often due to missing a required parameter
1002 | 400 | No value provided for mandatory resource
1003 | 400 | The specified resource type does not match the required type
1004 | 403 | The specified resource does not exist
1005 | 400 | The resource exceeds the maximum allowed value of {{MAX}}
1006 | 400 | The resource does not meet minimum required value of {{MIN}}
1007 | 400 | The resource does not match required size of {{SIZE}}
1008 | 409 | Invalid email
1009 | 400 | Invalid date format
1010 | 400 | Invalid XDC address
1011 | 400 | The specified resource is out of range
1012 | 409 | Invalid value
1101 | 401 | No valid API key provided
1102 | 400 | Too many requests hit the API too quickly
1103 | 409 | The specified account already exists
1104 | 403 | Server failed to authenticate the request
1105 | 500 | Internal Error
1106 | 500 | DB Error
1107 | 500 | Cannot send activation email to the user
1108 | 500 | Cannot unlock account
1109 | 500 | Cannot create new account
1110 | 500 | Cannot send forgot password/reset email to the user
1111 | 404 | Given email id does not exist
1112 | 404 | Reset Link Expired
1113 | 400 | Cannot change password. Enter correct detail
1115 | 500 | Something went wrong. Cannot process the request
1116 | 400 | Failed not enough balance
1117 | 400 | Account is invalid
1118 | 400 | Incorrect Password
1119 | 400 | Invalid OTP (2FA)
1120 | 400 | Cannot setup new account
1121 | 404 | Account does not exists
1122 | 400 | OTP Error
1123 | 400 | API Key is invalid
1124 | 400 | OTP Expired

#Versioning

Inorder to use v1.0 API version, use the following url address : <br>
<code>https://[host]/api/v1/[endpoint]</code>

