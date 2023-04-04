---
title: Reject FX Quote
---

### **Reject FX Quote**
[PUT /fx/{quoteUUID}/reject](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/fxapi/operation/rejectFXQuote/)

**HTTP Method: PUT**

**Description -** Sending a PUT request to **PUT /fx/{quoteUUID}/reject** endpoint allows user to reject FX Quote using quoteUUID in the path of the API request. All the request parameters and objects are mentioned below - 

**Request Parameters**



|**Name** |**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|quoteUUID|path|string|true|none|


**JSON Response**

A successful PUT request to this endpoint returns the following data -

**Response Code - 200**
```yaml Before
{
  "status": "Success or Failure",
  "code": "FXQUOTE003 etc.",
  "message": "Failed to reject a quote: ",
  "data": {
    "quoteUUID": "123e4567-e89b-12d3-a456-426614174000",
    "fxQuoteStatus": "Rejected"
  }
}

```
|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|status|string|false|none|This will return Success/Failed|
|code|string|false|none|This will indicate the error code in case of API error|
|message|string|false|none|This will be the detailed error message indicating what failed and how to fix the issue|
|data|<p>[FXRejectQuoteResponse_data](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/fxapi/operation/rejectFXQuote/)</p><p></p>|false|none|none|

**FX Reject Quote Response Data**
```yaml Before
{
  "quoteUUID": "123e4567-e89b-12d3-a456-426614174000",
  "fxQuoteStatus": "Rejected"
}

```
|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|quoteUUID|string|false|none|FX Quote universally unique identifier (UUID)|
|fxQuoteStatus|string|false|none|FX Quote status after rejection|