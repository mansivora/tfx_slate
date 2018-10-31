# Endpoints - Admin

Most of the endpoint require authentication of some type (user/API Key authentication). Where not required appropriate note will be provided.

<aside class="notice">
Authorization will expire and update after 24 hours .
</aside>


## Check Account Existence

Check Admin UserList.

### HTTP Request
<code>GET http://[host]/api/AdminUser/ListAll/0</code>


```shell
curl -X GET \
  'http://[host]/api/AdminUser/ListAll/0' \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
  -H 'authorization: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpYXQiOjE1NDA4MDcyOTksImV4cCI6MTU0MDg5MzY5OX0.ElthDyZJPXQ1xRMNjDU39AIXyaaB4z8V2TsMlPDS0nQ' \
```

> The JSON encoded response on successful request

```shell
{
        "UserID": 1,
        "FirstName": "test",
        "LastName": "test",
        "UserName": "testa",
        "Password": "test@123",
        "EmailID": "test@gmail.com",
        "MobileNo": "123456789",
        "IsActive": true,
        "CreateBy": 1,
        "CreateDate": "2018-10-30T01:25:03.030Z",
        "CreateIP": "::1",
        "UpdateBy": 1,
        "UpdateDate": "2018-10-30T01:34:52.723Z",
        "UpdateIP": "::1"
    }
```

### Parameters

Argument | Type | Required
-------|-------|-----
FirstName| String | yes
LastName| String | yes 
UserName| String | yes
Password| String | yes
EmailID| String | yes
IsActive| Boolean | yes
CreateBy| Integer | yes

## Create Admin Account

Create new account for Admin user.

### HTTP Request
<code>POST http://[host]/api/AdminUser/Add</code>


```shell
curl -X POST \
  http://[host]/api/AdminUser/Add \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
  -H 'authorization: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpYXQiOjE1NDA4MDcyOTksImV4cCI6MTU0MDg5MzY5OX0.ElthDyZJPXQ1xRMNjDU39AIXyaaB4z8V2TsMlPDS0nQ' \

  -d '{
		"FirstName": "test",
        "LastName": "test",
        "UserName": "test123@gmail.com",
        "Password": "test@123",
        "EmailID": "test123@gmail.com",
        "IsActive": true,
        "CreateBy": 4
   }'
```

> The JSON encoded response on successful account creation

```shell
{
	"result : success"
    }
```

### Parameters

Argument | Type | Required
-------|-------|-----
FirstName| String | yes
LastName| String | yes 
UserName| String | yes 
Password| String | yes 
EmailID| String | yes
IsActive| Boolean | yes
CreateBy| Integer | yes

## Update Admin Account

Update account for Admin user.

### HTTP Request
<code>PUT http://[host]/api/AdminUser/Update/<updatedby></code>


```shell
curl -X PUT \
  http://[host]/api/AdminUser/Update/<updatedby> \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
  -H 'authorization: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpYXQiOjE1NDA4MDcyOTksImV4cCI6MTU0MDg5MzY5OX0.ElthDyZJPXQ1xRMNjDU39AIXyaaB4z8V2TsMlPDS0nQ' \

  -d ' {
		"FirstName": "test",
        "LastName": "test",
        "UserName": "test123@gmail.com",
        "Password": "test@123",
        "EmailID": "test123@gmail.com",
        "IsActive": true,
        "UpdateBy": 4
   }'
```

> The JSON encoded response on successful account creation

```shell
{
	"result : success"
    }
```

### Parameters

Argument | Type | Required
-------|-------|-----
FirstName| String | yes
LastName| String | yes 
UserName| String | yes 
Password| String | yes 
EmailID| String | yes
IsActive| Boolean | yes
UpdateBy| Integer | yes
 

## Project Type List

Number of Project Type list existing 

### HTTP Request
<code>GET http://[host]/api/ProjectType/ListAll/0</code>


```shell
curl -X GET \
  http://[host]/api/ProjectType/ListAll/0 \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
  -H 'authorization: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpYXQiOjE1NDA4MDcyOTksImV4cCI6MTU0MDg5MzY5OX0.ElthDyZJPXQ1xRMNjDU39AIXyaaB4z8V2TsMlPDS0nQ' \
```

> The JSON encoded response on successful account creation

```shell
{
        "ProjectTypeID": 1,
        "ContractName": "Government",
        "IsDeleted": false,
        "CreateBy": 1,
        "CreateDate": "2018-10-30T14:25:18.847Z",
        "CreateIP": "192.168.1.1",
        "UpdateBy": 1,
        "UpdateDate": "2018-10-30T17:16:16.020Z",
        "UpdateIP": "::ffff:86.98.6.219"
    }

```

### Parameters

Argument | Type 
-------|-------
ProjectTypeID| Integer 
ContractName| String  
IsDeleted| String  
CreateBy| Integer  

## Add Project Type 

Add new Project Type 

### HTTP Request
<code>POST http://[host]/api/ProjectType/Add</code>


```shell
curl -X POST \
  http://[host]/api/ProjectType/Add \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
  -H 'authorization: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpYXQiOjE1NDA4MDcyOTksImV4cCI6MTU0MDg5MzY5OX0.ElthDyZJPXQ1xRMNjDU39AIXyaaB4z8V2TsMlPDS0nQ' \
  -d '
	{
		"ContractName": "Government",
        "IsDeleted": false,
        "CreateBy": 1
    }
```

> The JSON encoded response on successful account creation

```shell
{
	"result : success"
    }

```

### Parameters

Argument | Type | Required
-------|-------|-----
ContractName| String | yes
IsDeleted| Boolean | yes 
CreateBy| Integer | yes 

## Update Project Type

Update Project Type.

### HTTP Request
<code>PUT http://[host]/api/ProjectType/Update/<updatedby></code>


```shell
curl -X PUT \
  http://[host]/api/ProjectType/Update/<updatedby> \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
  -H 'authorization: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpYXQiOjE1NDA4MDcyOTksImV4cCI6MTU0MDg5MzY5OX0.ElthDyZJPXQ1xRMNjDU39AIXyaaB4z8V2TsMlPDS0nQ' \

  -d ' 	{
		"ContractName": "Private",
        "IsDeleted": "true",
        "UpdateBy": 1
    }'
```

> The JSON encoded response on successful account creation

```shell
{
	"result : success"
    }
```
### Parameters

Argument | Type | Required
-------|-------|-----
ContractName| String | yes
IsDeleted| Boolean | yes 
UpdateBy| Integer | yes 


## Sector List

Number of Sector list existing

### HTTP Request
<code>GET http://[host]/api/Sector/ListAll/0</code>


```shell
curl -X GET \
  http://[host]/api/Sector/ListAll/0 \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
  -H 'authorization: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpYXQiOjE1NDA4MDcyOTksImV4cCI6MTU0MDg5MzY5OX0.ElthDyZJPXQ1xRMNjDU39AIXyaaB4z8V2TsMlPDS0nQ' \
```

> The JSON encoded response on successful account creation

```shell
{
        "SectorID": 3,
        "SkillName": "testName",
        "ImagePath": "folder/Image.jpg",
        "IndustryID": 1,
        "IsDeleted": false,
        "CreateBy": 1,
        "CreateDate": "2018-10-30T11:38:45.137Z",
        "CreateIP": "::ffff:103.43.160.22",
        "UpdateBy": 1,
        "UpdateDate": "2018-10-30T11:38:45.137Z",
        "UpdateIP": "::ffff:103.43.160.22",
        "IndustryName": "Renewable"
    }
```

### Parameters

Argument | Type 
-------|-------
SkillName| String 
ImagePath| Image  
IndustryName| String  
IsDeleted| Boolean 
CreateBy| Integer 

## Add Sector 

Add new Sector 

### HTTP Request
<code>POST http://[host]/api/Sector/Add</code>


```shell
curl -X POST \
  http://[host]/api/Sector/Add \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
  -H 'authorization: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpYXQiOjE1NDA4MDcyOTksImV4cCI6MTU0MDg5MzY5OX0.ElthDyZJPXQ1xRMNjDU39AIXyaaB4z8V2TsMlPDS0nQ' \
  -d '
		{
		"SkillName": "testName",
        "ImagePath": "folder/Image.jpg",
        "IndustryName": "Renewable",
        "IsDeleted": false,
        "CreateBy": 1
    }'
```

> The JSON encoded response on successful account creation

```shell
{
	"result : success"
    }

```

### Parameters
Argument | Type | Required
-------|-------|-----
SkillName| String | yes
ImagePath| Image | yes 
IndustryName| String | yes 
IsDeleted| Boolean | yes
CreateBy| Integer | yes

## Update Sector

Update Sector.

### HTTP Request
<code>PUT http://[host]/api/Sector/Update/<updatedby></code>


```shell
curl -X PUT \
  http://[host]/api/Sector/Update/<updatedby> \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
  -H 'authorization: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpYXQiOjE1NDA4MDcyOTksImV4cCI6MTU0MDg5MzY5OX0.ElthDyZJPXQ1xRMNjDU39AIXyaaB4z8V2TsMlPDS0nQ' \

  -d ' 	{
		"SkillName": "testName",
        "ImagePath": "folder/Image.jpg",
        "IndustryName": "Renewable",
        "IsDeleted": false,
        "UpdateBy": 1
    }'
```

> The JSON encoded response on successful account creation

```shell
{
	"result : success"
    }
```
### Parameters

Argument | Type | Required
-------|-------|-----
SkillName| String | yes
ImagePath| Image | yes 
IndustryName| String | yes 
IsDeleted| Boolean | yes
UpdateBy| Integer | yes


## Industry

Number of Industry list existing

### HTTP Request
<code>GET http://[host]/api/Industry/ListAll/0</code>


```shell
curl -X GET \
  http://[host]/api/Industry/ListAll/0 \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
  -H 'authorization: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpYXQiOjE1NDA4MDcyOTksImV4cCI6MTU0MDg5MzY5OX0.ElthDyZJPXQ1xRMNjDU39AIXyaaB4z8V2TsMlPDS0nQ' \
```

> The JSON encoded response on successful account creation

```shell
{
        "IndustryID": 1,
        "IndustryName": "Energy",
        "ImagePath": "dsjkh/sdfds.jpg",
        "IsDeleted": false,
        "CreateBy": 1,
        "CreateDate": "2018-10-301:55:02.263Z",
        "CreateIP": "::1",
        "UpdateBy": 1,
        "UpdateDate": "2018-10-301:56:42.840Z",
        "UpdateIP": "::1"
    }```

### Parameters

Argument | Type 
-------|-------
IndustryName| String 
ImagePath| Image    
IsDeleted| Boolean 
CreateBy| Integer 

## Add Industry

Add new Industry

### HTTP Request
<code>POST http://[host]/api/Industry/Add</code>


```shell
curl -X POST \
  http://[host]/api/Industry/Add \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
  -H 'authorization: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpYXQiOjE1NDA4MDcyOTksImV4cCI6MTU0MDg5MzY5OX0.ElthDyZJPXQ1xRMNjDU39AIXyaaB4z8V2TsMlPDS0nQ' \
  -d '
		{
  		"IndustryName": "RTA",
        "ImagePath": "folder/image.jpg",
        "IsDeleted": false,
        "CreateBy": 1
	}```

> The JSON encoded response on successful account creation

```shell
{
	"result : success"
    }

```

### Parameters
Argument | Type | Required
-------|-------|-----
IndustryName| String | yes
ImagePath| Image | yes  
IsDeleted| Boolean | yes
CreateBy| Integer | yes

## Update Industry

Update Industry.

### HTTP Request
<code>PUT http://[host]/api/Industry/Update/<updatedby></code>


```shell
curl -X PUT \
  http://[host]/api/Industry/Update/<updatedby> \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
  -H 'authorization: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpYXQiOjE1NDA4MDcyOTksImV4cCI6MTU0MDg5MzY5OX0.ElthDyZJPXQ1xRMNjDU39AIXyaaB4z8V2TsMlPDS0nQ' \

  -d ' 		{
  		"IndustryName": "IT Industry",
        "ImagePath": "folder/image.jpg",
        "IsDeleted": false,
        "UpdateBy": 1
	}'
```

> The JSON encoded response on successful account creation

```shell
{
	"result : success"
    }
```
### Parameters

Argument | Type | Required
-------|-------|-----
IndustryName| String | yes
ImagePath| Image | yes  
IsDeleted| Boolean | yes
UpdateBy| Integer | yes


























