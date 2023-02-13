---
title: Finzly Payout
---

### **Create Credit Payment**
[POST /payments/creditrequest](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/createCreditPaymentV3/)

**HTTP Method: POST**

**Description -** Sending a POST request to **//payments/creditrequest** endpoint allows users to submit domestic or international one time or recurring payments. All the request parameters and objects are specified below:

**Request Parameters**

All details of the users to which we want to make the payment will be passed in the body of the API request.


|**Name**|**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|body|body|[CreditPaymentRequest](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/createCreditPaymentV3/)|true|Payment fields|


**JSON Response**

A successful POST request to this endpoint will return the following data-

**Success Code - 200**

```yaml Before
{
  "status": "Success or Failure",
  "code": "PAYMENT001 etc.",
  "message": "Failed to create a payment: ",
  "data": {
    "paymentUID": "string",
    "paymentStatus": "string",
    "externalReferenceId": "string"
  }
}

```

|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|status|string|false|none|Status of the API request either it will be a success or a failure|
|code|string|false|none|Code associated with the error.|
|message|string|false|none|Error message corresponding to the error code indicating the issue in API call and an indication on how to resolve it.|
|data|[BookTransferResponse_data](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/createCreditPaymentV3/)|false|none|none|

<!-- **Book Transfer Response Data**
```yaml Before
{
  "paymentUID": "string",
  "paymentStatus": "string",
  "externalReferenceId": "string"
}
``` -->

|Name|Type|Required|Restrictions|Description|
| :- | :- | :- | :- | :- |
|paymentUID|string|false|none|none|
|paymentStatus|string|false|none|none|
|externalReferenceId|string|false|none|none|