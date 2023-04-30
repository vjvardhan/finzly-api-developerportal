---
title: Return a Payment
---

### **Return a payment**

You can return a payment using this API if the payment rail supports the return of payments.

<br>

[PUT/payments/{paymentUID}/return](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/paymentapi/operation/returnPaymentV3/)

**HTTP Method: PUT**

**Description -** Sending a PUT request to "/payments/{paymentUID}/return" endpoint allows users to return a payment. All the request parameters and objects are specified below

**Request Parameters**

|**Name**|**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|paymentUID|path|string|true|none|
|body|body|[ReturnPaymentRequest](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/paymentapi/operation/returnPaymentV3/)|false |Payment unique reference ID|

**ReturnPaymentRequest**

```yaml Before
{
  "achReturnCode": "R01",
  "returnNotes": "Invalid payment request."
}

```

|**Name**|**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|achReturnCode|request|string|true|Payment return code|
|returnNotes|request|string|true|Payment return description|


**JSON Response**

**Success Code - 200**

```yaml Before

{
  "status": "Success or Failure",
  "code": "PAYMENT003 etc.",
  "message": "Failed to return a payment: ",
  "data": {
    "paymentUID": "string",
	"status": "string"
  }
}

```

|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|status|string|false|none|Status of the API request either it will be a success or a failure|
|code|string|false|none|Code associated with the error.|
|message|string|false|none|Error message corresponding to the error code indicating the issue in API call and an indication on how to resolve it.|
|data|ReturnPaymentResponse_data|false|none|Return Response Data|


**ReturnPaymentResponse_data**

```yaml Before
{
  "paymentUID": "string",
  "status": "string"
}

```

|**Name**|**Type**|**Description**|
| :- | :- | :- |
|paymentUID|string|Payment unique preference ID|
|status|string|Payment response status|