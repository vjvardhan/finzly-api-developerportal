---
title: Finzly Application API
---



## **Applications**
### **Get Application**
[GET /applications](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/userreference/operation/getApplication/)

**HTTP Method: GET**

**Description -** Sending a GET request to GET/applications endpoint allows users to fetch the application details using parameters “type” and “status” as a query in the API request.

Request Parameters

**The Application Type and status are optional parameters to be passed in the query of API request.**

|**Name** |**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|type|query|string|false|Application Type|
|status|query|string|false|Application Status|


Enumerated Values

|**Parameter**|**Value**|
| :- | :- |
|type|BANK|
|type|CUSTOMER|
|status|ACTIVE|
|status|INACTIVE|

**JSON Response**

**A successful GET request to this endpoint will return the following data -** 

```yaml Before
{
  "status": "Success or Failure",
  "code": "APP001 etc.",
  "message": "Failed to get an application: .",
  "data": [
    {
      "appCode": "finzly.payment etc.",
      "description": "Payment Hub etc.",
      "status": "ACTIVE or INACTIVE",
      "type": "BANK or CUSTOMER",
      "entilements": [
        {
          "UUID": "string",
          "entitlementCode": "aBlkFil etc.",
          "description": "string"
        }
      ]
    }
  ]
}
```
**Data Returned**


|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|status|string|false|none|This will return Success/Failed|
|code|string|false|none|This will indicate the error code in case of API error|
|message|string|false|none|This will be the detailed error message indicating what failed and how to fix the issue|
|data|[[SearchApplication](https://apidocs.finzly.net/dashboard?java=#schemasearchapplication)]|false|none|none|

Get Application Details By App Code	

[GET /applications/appcode/{app-code}](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/userreference/operation/getApplicationDetailsByAppCode/)

**HTTP Method: GET**

**Description-** Sending a GET request to **/applications/appcode/{app-code}** endpoint allows users to get application details by the application code by providing app-code in the path of the API request.

**Request Parameters**

The App-code needs to be passed in the path of the API request


|**Name** |**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|app-code|path|string|true|none|


**JSON Response**

**A successful GET request to this endpoint returns the following data -** 

```yaml Before
{
  "status": "Success or Failure",
  "code": "APP001 etc.",
  "message": "Failed to get an application: .",
  "data": [
    {
      "appCode": "finzly.payment etc.",
      "description": "Payment Hub etc.",
      "status": "ACTIVE or INACTIVE",
      "type": "BANK or CUSTOMER",
      "entilements": [
        {
          "UUID": "string",
          "entitlementCode": "aBlkFil etc.",
          "description": "string"
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
|status|string|false|none|This will return Success/Failed|
|code|string|false|none|This will indicate the error code in case of API error|
|message|string|false|none|This will be the detailed error message indicating what failed and how to fix the issue|
|data|[Application]|false|none|none|

