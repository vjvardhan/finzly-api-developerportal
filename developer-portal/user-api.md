---
title: Finzly User API
---


## Users Management

### **Search User**	

[POST /users/search](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/userreference/operation/searchUser/)

**HTTP Method: POST**

**Description -** Sending a POST request to **/users/search endpoint allows users to** search users by the given request criteria. This API will return user profile data without role and user limit details. All the request parameters and objects are mentioned below - 


|**Name**|**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|body|body|[/SearchUserRequest](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/userreference/operation/searchUser/)|true|Customer User|

**JSON Response**

**A successful POST request to this endpoint returns the following data -** 

```yaml Before
{
  "status": "Success or Failure",
  "code": "USER001 etc.",
  "message": "Failed to get the users: .",
  "data": [
    {
      "userUUID": "for e.g. 123e4567-e89b-12d3-a456-426614174000",
      "userName": "for e.g. user001",
      "firstName": "for e.g. John",
      "lastName": "for e.g. Doe",
      "department": "for e.g. payments",
      "otherDepartments": [
        "for e.g. [admin,BSA]"
      ],
      "customerUID": "1223",
      "emulationUser": "YES or NO",
      "customerShortName": "DEMOBANK",
      "status": "Active or Suspended etc.",
      "email": "test@bank.com",
      "mobile": "12345678",
      "type": "BANK or CUSTOMER",
      "createdBy": "ABC001",
      "lastUpdatedBy": "XYZ001"
    }
  ],
  "pagination": {
    "totalRecords": 100,
    "returnedRecords": 10,
    "pageReturned": 2,
    "pageSize": 10
  }
}
```
|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|status|string|false|none|This will return Success/Failed|
|code|string|false|none|This will indicate the error code in case of API error|
|message|string|false|none|This will be the detailed error message indicating what failed and how to fix the issue|
|data|[[/SearchUser](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/userreference/operation/searchUser/)]|false|none|none|
|pagination|[/Pagination](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/userreference/operation/searchUser/)|false|none|none|

### **Get User /**

[GET /users/{userUUID}](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/userreference/operation/searchUser/)

**HTTP Method: GET**

**Description -**  Sending a GET request to this ID /users/{userUUID} allows users to get the user by userUUID. This API will return user profile data along with role and user limit details. All the request parameters and objects are mentioned below - 


|**Name**|**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|userUUID|path|string|true|A universally unique identifier (UUID) associated with the user|
|type|query|string|true|Type of the user|

**Enumerated Values**


|**Parameter**|**Value**|
| :- | :- |
|type|CUSTOMER|
|type|BANK|

**JSON Response -** 

**A successful GET request this endpoint returns the following data**

```yaml Before

{
  "userUUID": "for e.g. 123e4567-e89b-12d3-a456-426614174000",
  "userName": "for e.g. user001",
  "firstName": "for e.g. John",
  "lastName": "for e.g. Doe",
  "department": "for e.g. payments",
  "otherDepartments": [
    "for e.g. [admin,BSA]"
  ],
  "customerUID": "1223",
  "emulationUser": "YES or NO",
  "customerShortName": "DEMOBANK",
  "status": "Active or Suspended etc.",
  "email": "test@bank.com",
  "mobile": "12345678",
  "type": "BANK or CUSTOMER",
  "createdBy": "ABC001",
  "lastUpdatedBy": "XYZ001",
  "roles": [
    {
      "roleUUID": "123e4567-e89b-12d3-a456-426614174000",
      "name": "AdminRole",
      "description": "Bank admin permission",
      "applications": [
        {
          "appCode": "for e.g. finzly.payment",
          "description": "for e.g. Payment Hub application to process multiple payment rails",
          "entitlements": [
            {
              "entitlement": "for e.g. ApprovePayment",
              "description": "Allow user to approve the payment"
            }
          ]
        }
      ]
    }
  ],
  "userlimits": [
    {
      "limitCode": "ACH_USER_BULK_FILE_APPROVAL_LIMIT etc.",
      "value": "10000 etc.",
      "description": "ACH user bulk file approval limit etc.",
      "appCode": "finzly.payments etc.",
      "linkedEntitlementCode": "aBlkFil etc."
    }
  ]
}

```



|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|userUUID|string|false|none|A universally unique identifier (UUID) assigned by the system|
|userName|string|false|none|Unique username assigned to the user|
|firstName|string|false|none|User First Name|
|lastName|string|false|none|User Last Name|
|department|string|false|none|Primary bank department user is associated with|
|otherDepartments|[string]|false|none|none|
|customerUID|string|false|none|Unique id associated with the CRM entity|
|emulationUser|string |false|none|If the user has an emulation capability. This is applicable for CUSTOMER user types.|
|customerShortName|string|false|none|Customer short name|
|status|string|false|none|User Status|
|email|string|false|none|Customer email address|
|mobile|string|` `false|none|Customer mobile contact number|
|type|string|false|none|Type of user|
|createdBy|string|false|none|User Id who created the user in the system|
|lastUpdatedBy|string|false|none|User who last updated the user in the system|
|roles|[[/UserRole](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/userreference/operation/searchUser/)]|false|none|none|
|userlimits|<p>[[/UserLimits](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/userreference/operation/searchUser/)]</p><p></p>|false|none|none|

### **Update User**

[PUT /users](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/userreference/operation/updateUser/)

**HTTP Method: PUT**

**Description -** Sending a PUT request to PUT /users allows users to update an existing user. The request parameters and objects are mentioned below -

**Request Parameters**


|Name|In|Type|Required|Description|
| :- | :- | :- | :- | :- |
|body|body|<p>[/UpdateUserRequest](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/userreference/operation/updateUser/)</p><p></p>|false|Customer User|

**JSON Response**

**A successful PUT request to this endpoint returns the following data -** 

```yaml Before
{
  "status": "Success or Failure",
  "code": "USER001 etc.",
  "message": "Failed to add an user: .",
  "data": {
    "externalReferenceId": "string",
    "userUUID": "123e4567-e89b-12d3-a456-426614174000"
  }
}

```
|Name|Type|Required|Restrictions|Description|
| :- | :- | :- | :- | :- |
|status|string|false|none|This will return Success/Failed|
|code|string|false|none|This will indicate the error code in case of API error|
|message|string|false|none|This will be the detailed error message indicating what failed and how to fix the issue|
|data|[/AddUserResponseData](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/userreference/operation/updateUser/)|false|none|none|


**/ Add User Response**
```yaml Before
{
  "externalReferenceId": "string",
  "userUUID": "123e4567-e89b-12d3-a456-426614174000"
}

```


|Name|Type|Required|Restrictions|Description|
| :- | :- | :- | :- | :- |
|externalReferenceId|string|false|none|Unique reference id from a system outside of the Finzly system.|
|userUUID|string|false|none|A universally unique identifier (UUID) assigned to the user by the system|


### **Add User**

[POST /users](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/userreference/operation/addUser/)

**HTTP Method: POST**

**Description -** Sending a POST request to POST /users endpoint allows users to add a new user to the system. The request parameters and objects are mentioned below

Request Parameters


|Name|In|Type|Required|Description|
| :- | :- | :- | :- | :- |
|body|body|<p>[/UpdateUserRequest](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/userreference/operation/addUser/)</p><p></p>|false|Customer User|

**JSON Response**

**A successful POST request to this endpoint returns the following data -**
```yaml Before

{
  "status": "Success or Failure",
  "code": "USER001 etc.",
  "message": "Failed to add an user: .",
  "data": {
    "externalReferenceId": "string",
    "userUUID": "123e4567-e89b-12d3-a456-426614174000"
  }
}

```

|Name|Type|Required|Restrictions|Description|
| :- | :- | :- | :- | :- |
|status|string|false|none|This will return Success/Failed|
|code|string|false|none|This will indicate the error code in case of API error|
|message|string|false|none|This will be the detailed error message indicating what failed and how to fix the issue|
|data|[/AddUserResponseData](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/userreference/operation/addUser/)|false|none|none|

**/ Add User Response**
```yaml Before
{
  "externalReferenceId": "string",
  "userUUID": "123e4567-e89b-12d3-a456-426614174000"
}

```




|Name|Type|Required|Restrictions|Description|
| :- | :- | :- | :- | :- |
|externalReferenceId|string|false|none|Unique reference id from a system outside of the Finzly system.|
|userUUID|string|false|none|A universally unique identifier (UUID) assigned to the user by the system|

### **Activate User**
[PUT /users/{userUUID}/activate](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/userreference/operation/activateUser/)
**HTTP Method: PUT**

**Description -** Sending a PUT request to the PUT /users/{userUUID}/activate endpoint allows users to activate a user. The request parameters and objects are mentioned below - 

**Request Parameters**


|Name|In|Type|Required|Description|
| :- | :- | :- | :- | :- |
|userUUID|path|string|true|A universally unique identifier (UUID) assigned to the user|
|type |query |string|true|user type|

**Enumerated Values**


|**Parameter**|**Value**|
| :- | :- |
|type|BANK|
|type|CUSTOMER|


**JSON Response**

**A successful PUT request to this endpoint returns the following data**
```yaml Before
{
  "status": "Success or Failure",
  "code": "USER001 etc.",
  "message": "Failed to activate or suspend the user: ."
}

```
|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|status|string|false|none|This will return Success/Failed|
|code|string|false|none|This will indicate the error code in case of API error|
|message|string|false|none|This will be the detailed error message indicating what failed and how to fix the issue|


### **Suspend User /**

[PUT /users/{userUUID}/suspend](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/userreference/operation/suspendUser/)

**HTTP Method: PUT**

**Description -** Sending a PUT request to  /users/{userUUID}/suspend endpoint allows users to suspend a user by passing userUUID in the path of the API request. The request parameters and objects are mentioned below - 

Request Parameters


|Name|In|Type|Required|Description|
| :- | :- | :- | :- | :- |
|userUUID|path|string|true|A universally unique identifier (UUID) assigned to the user|
|type |query |string|true|user type|

**Enumerated Values**


|**Parameter**|**Value**|
| :- | :- |
|type|BANK|
|type|CUSTOMER|


**JSON Response**

**A successful PUT request to this endpoint returns the following data** 

```yaml Before
{
  "status": "Success or Failure",
  "code": "USER001 etc.",
  "message": "Failed to activate or suspend the user: ."
}


```



|Name|Type|Required|Restrictions|Description|
| :- | :- | :- | :- | :- |
|status|string|false|none|This will return Success/Failed|
|code|string|false|none|This will indicate the error code in case of API error|
|message|string|false|none|This will be the detailed error message indicating what failed and how to fix the issue|
