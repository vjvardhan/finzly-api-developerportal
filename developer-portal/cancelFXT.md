---
title: Cancel FX Trade
---

### **Cancel FX Trade**
[DELETE /fx/{forexContractNo}/cancel](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/fxapi/operation/cancelFXTrade/)

**HTTP Method: Delete**

**Description -** Sending a DELETE request to the **/fx/{forexContractNo}/cancel** endpoint allows users to cancel FX trade by passing the forexContractNo in the path of the API request. All the parameters and objects are specified below - 

**Request Parameters**


|**Name** |**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|forexContractNo|path|string|true|none|

**JASON Response**

A successful Delete request to this endpoint returns the following data -

**Response Code - 200**

```yaml Before
{
  "status": "Success or Failure",
  "code": "FX001 etc.",
  "message": "Failed to cancel a trade: ",
  "data": {
    "forexContractNo": "123898",
    "tradeStatus": "Cancelled etc."
  }
}

```

|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|status|string|false|none|This will return Success/Failed|
|code|string|false|none|This will indicate the error code in case of API error|
|message|string|false|none|This will be the detailed error message indicating what failed and how to fix the issue|
|data|<p>[FXTradeCancelResponse_data](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/fxapi/operation/cancelFXTrade/)</p><p></p>|false|none|none|

**FX Trade Cancel Response Data**
```yaml Before
{
  "forexContractNo": "123898",
  "tradeStatus": "Cancelled etc."
}
```

|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|forexContractNo|string|false|none|FX contract number assigned by the system for a given trade.|
|tradeStatus|string|false|none|Trade status after trade cancelation|