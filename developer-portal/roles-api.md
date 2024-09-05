---
title: Finzly Roles API
---

## Roles Management

### **Search Roles**

[POST/searchRole/](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/userreference/operation/searchRole/)

**HTTP Method: POST**

**Description:** Sending a POST request to /searchRole/ endpoint allows users to search roles created by business customers to support their internal users. All the request parameters and objects are mentioned below - 

**Request Parameters**



|**Name** |**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|body|body|[/GetRoleRequest](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/userreference/operation/searchRole/)|true|Search the roles using various parameters|


**JSON Response**

**A successful POST request to this endpoint returns the following data -** 

```yaml Before
{
  "status": "Success or Failure",
  "code": "ROLE001 etc.",
  "message": "Failed to get roles: .",
  "data": [
    {
      "roleUUID": "123e4567-e89b-12d3-a456-426614174000 etc.",
      "roleName": "User Admin etc.",
      "description": "User Administrative role etc.",
      "type": "BANK or CUSTOMER",
      "customerUID": 0,
      "customerShortName": "XYZCO etc.",
      "applications": [
        {
          "appCode": "finzly.payment etc.",
          "status": "ACTIVE or INACTIVE",
          "entilements": [
            {
              "entitlementCode": "string"
            }
          ],
          "userLimits": [
            {
              "limitCode": "ACH_USER_BULK_FILE_APPROVAL_LIMIT etc.",
              "value": "10000 etc.",
              "description": "ACH user bulk file approval limit etc.",
              "appCode": "finzly.payments etc.",
              "linkedEntitlementCode": "aBlkFil etc."
            }
          ]
        }
      ]
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
|data|[[/Role](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/userreference/operation/searchRole/)]|false|none|none|
|pagination|[/Pagination](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/userreference/operation/searchRole/)|false |none|none|


**/Role**
```yaml Before
{
  "roleUUID": "123e4567-e89b-12d3-a456-426614174000 etc.",
  "roleName": "User Admin etc.",
  "description": "User Administrative role etc.",
  "type": "BANK or CUSTOMER",
  "customerUID": 0,
  "customerShortName": "XYZCO etc.",
  "applications": [
    {
      "appCode": "finzly.payment etc.",
      "status": "ACTIVE or INACTIVE",
      "entilements": [
        {
          "entitlementCode": "string"
        }
      ],
      "userLimits": [
        {
          "limitCode": "ACH_USER_BULK_FILE_APPROVAL_LIMIT etc.",
          "value": "10000 etc.",
          "description": "ACH user bulk file approval limit etc.",
          "appCode": "finzly.payments etc.",
          "linkedEntitlementCode": "aBlkFil etc."
        }
      ]
    }
  ]
}

```


|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|roleUUID|string|false|none|A UUID (Universal Unique Identifier) associated with the role|
|roleName|string|false|none|Name of the role|
|description|string|false|none|Role details|
|type|string|false|none|Type of the Role|
|customerUID|number|false |none|A unique id associated with the CRM entity|
|customerShortName|string|false|none|Short name associated with the CRM entity|
|applications|[/App]|false|none|none|


### **Add Role /**

[POST /roles](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/userreference/operation/addRole/)

**HTTP Method: POST**

**Description -** Sending a POST request to POST /roles endpoint allows users to add a new role. All the request parameters and objects are mentioned below - 

Request Parameters



|**Name** |**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|body|body|[/CreateRoleRequest](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/userreference/operation/addRole/)|true|Search the roles using various parameters|

**JSON Response**

Sending a successful POST request to this endpoint returns the following data - 

```yaml Before

{
  "status": "Success or Failure",
  "code": "ROLE001 etc.",
  "message": "Failed to add a role: .",
  "data": {
    "externalReferenceId": "for e.g. 126879",
    "roleUUID": "for e.g. 123e4567-e89b-12d3-a456-426614174000"
  }
}


```

|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|status|string|false|none|This will return Success/Failed|
|code|string|false|none|This will indicate the error code in case of API error|
|message|string|false|none|This will be the detailed error message indicating what failed and how to fix the issue|
|data|[/CreateRoleResponse_data](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/userreference/operation/addRole/)|false|none|none|

**/ Create Role Response Data**
```yaml Before
{
  "externalReferenceId": "for e.g. 126879",
  "roleUUID": "for e.g. 123e4567-e89b-12d3-a456-426614174000"
}
```
|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|externalReferenceId|string|false|none|An external reference id|
|roleUUID|string|false|none|A UUID associated with the role|


### **Get Role**

[GET /roles/{roleUUID}](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/userreference/operation/getRole/)

HTTP Method: GET**

**Description -** Sending a GET request to **/roles/{roleUUID}** allows users to retrieve a role details by a role id by passing roleUUID in the path of the API request. All the request parameters and objects are mentioned below - 

**Request Parameters**

**RoleUUID needs to be passed in the path of the API request.**


|**Name**|**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|roleUUID|path|string|true|A UUID (Universal Unique Identifier) associated with a role|
|type|query|string|false|Type of the role|

**Enumerated Values**

|**Parameter**|**Value**|
| :- | :- |
|type|CUSTOMER|
|type|BANK|

**JSON Response**

**A successful GET request to this endpoint returns the following data -** 

```yaml Before
{
  "status": "Success or Failure",
  "code": "ROLE001 etc.",
  "message": "Failed to find a role: .",
  "data": {
    "roleUUID": "123e4567-e89b-12d3-a456-426614174000 etc.",
    "roleName": "User Admin etc.",
    "description": "User Administrative role etc.",
    "type": "BANK or CUSTOMER",
    "customerUID": 0,
    "customerShortName": "XYZCO etc.",
    "applications": [
      {
        "appCode": "finzly.payment etc.",
        "status": "ACTIVE or INACTIVE",
        "entilements": [
          {
            "entitlementCode": "string"
          }
        ],
        "userLimits": [
          {
            "limitCode": "ACH_USER_BULK_FILE_APPROVAL_LIMIT etc.",
            "value": "10000 etc.",
            "description": "ACH user bulk file approval limit etc.",
            "appCode": "finzly.payments etc.",
            "linkedEntitlementCode": "aBlkFil etc."
          }
        ]
      }
    ]
  }
}

```

|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|status|string|false|none|This will return Success/Failed|
|code|string|false|none|This will indicate the error code in case of API error|
|message|string|false|none|This will be the detailed error message indicating what failed and how to fix the issue|
|data|[/Role](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/userreference/operation/getRole/)|false|none|none|

**/Role**

|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|roleUUID|string|false|none|A UUID (Universal Unique Identifier) associated with the role|
|roleName|string|false|none|Name of the role|
|description|string|false|none|Role details|
|type|string|false|none|Type of the Role|
|customerUID|number|false |none|A unique id associated with the CRM entity|
|customerShortName|string|false|none|Short name associated with the CRM entity|
|applications|[/App]|false|none|none|

### **Update Role /**

[PUT /roles/{roleUUID}](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/userreference/operation/updateRole/)

**HTTP Method:  PUT**

**Description** - Sending a PUT request to PUT /roles/{roleUUID} allows users to update a role by passing roleUUID in the path of the API request.

**Request Parameters**


|**Name**|**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|roleUUID|path|string|true|A UUID (Universal Unique Identifier) associated with a role|
|body|body|<p></p><p>[/CreateRoleRequest](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/userreference/operation/updateRole/)</p>|false|Type of the role|

**JSON Response**

**A successful PUT request to this endpoint returns the following data -** 

```yaml Before
{
  "status": "Success or Failure",
  "code": "ROLE001 etc.",
  "message": "Failed to add a role: .",
  "data": {
    "externalReferenceId": "for e.g. 126879",
    "roleUUID": "for e.g. 123e4567-e89b-12d3-a456-426614174000"
  }
}

```



|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|status|string|false|none|This will return Success/Failed|
|code|string|false|none|This will indicate the error code in case of API error|
|message|string|false|none|This will be the detailed error message indicating what failed and how to fix the issue|
|data|[/CreateRoleResponse_data](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/userreference/operation/updateRole/)|false|none|none|

### **Delete Role**

[DELETE /roles/{roleUUID}](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/userreference/operation/deleteRole/)

**HTTP Method: DELETE**

**Description -** Sending a DELETE request to /roles/{roleUUID} endpoint allows users to delete a role by passing roleUUID in the path of the API request. All the parameters and objects are mentioned below - 



|**Name**|**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|body|body|<p>[/GetRoleRequest](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/userreference/operation/deleteRole/)</p><p></p>|true|Search the roles using various parameters|

**JSON Response**

**A successful DELETE request to this endpoint returns the following data -** 

```yamle Before

{
  "status": "Success or Failure",
  "code": "ROLE001 etc.",
  "message": "Failed to delete a role: .",
  "data": {
    "roleUUID": "for e.g. 123e4567-e89b-12d3-a456-426614174000"
  }
}



```




|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|status|string|false|none|This will return Success/Failed|
|code|string|false|none|This will indicate the error code in case of API error|
|message|string|false|none|This will be the detailed error message indicating what failed and how to fix the issue|
|data|[/DeleteRoleResponse_data](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/userreference/operation/deleteRole/)|false|none|none|

**/ Delete Roles Response**
```yaml Before
{
  "roleUUID": "for e.g. 123e4567-e89b-12d3-a456-426614174000"
}

```




|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|roleUUID|string|false|none|A UUID associated with the role|