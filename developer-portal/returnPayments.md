---
title: Return Payments
---

### **Return a payment**

You can use below API to return a payment as long as it allowed as per the payment rail return rules.


[PUT/payments/{paymentUID}/return](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/returnPaymentV3/)

**HTTP Method: PUT**

**Description -** Sending a PUT request to "/payments/{paymentUID}/return" endpoint allows users to return a payment. All the request parameters and objects are specified below

**Request Parameters**

|**Name**|**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|paymentUID|path|string|true|none|
|body|body|[ReturnPaymentRequest](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/returnPaymentV3/)|false |Payment unique refrence ID|

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
  "code": "PAYMENT001 etc.",
  "message": "Failed to cancel a payment: ",
  "data": {
    "paymentUID": "string"
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
  "paymentUID": "string"
}

```

|**Name**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|paymentUID|string|false|Payment unique refrence ID|