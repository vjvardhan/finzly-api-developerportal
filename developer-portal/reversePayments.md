---
title: Reverse Payments
---

### **Reverse a Payment**

You can use below API to reverse a payment as long as it allowed as per the payment rail rules.


[PUT /payments/{paymentUID}/reverse](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/reversePaymentV3/)

**HTTP Method: PUT**

**Description -** Sending a PUT request to "/payments/{paymentUID}/reverse" endpoint allows users to reverse a payment. All the request parameters and objects are specified below

**Request Parameters**


|**Name**|**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|paymentUID|path|string|true|Payment unique identifier|
|ReversePaymentRequest|body|ReversePaymentRequest|false |Reverse payment response|

**ReversePaymentRequest**

```yaml Before
{
  "reversalNotes": "" 
}
```

|**Name**|**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|reversalNotes|request|string|false|Reversal notes|

**JSON Response**

**Success Code - 200**

```yaml Before

{
  "status": "Success or Failure",
  "code": "PAYMENT003 etc.",
  "message": "Failed to reverse a payment: ",
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
|data|ReversePaymentResponse_data|false|none|Reverse Payment Response Data|


**ReversePaymentResponse_data**

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
