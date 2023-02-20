---
title: Cancel Payment
---

### **Cancel a Payment**

You can use below API to cancel a payment as long as it does not send to the payment network. Once the payment is tranmitted to the respective payment network user can't cancel the payment.

[PUT /payments/{paymentUID}/cancel](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/cancelPaymentV3/)

**HTTP Method: PUT**	

**Description-** Sending a PUT Request to "/payments/{paymentUID}/cancel" endpoint allows users to cancel a payment.using paymentUID. All the request parameters and objects are specified below -

**Request Parameters**


|**Name**|**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|paymentUID|path|string|true|Payment unique refrence ID|

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
|data|CancelPaymentResponse_data|false|none|Cancel Response Data|


**CancelPaymentResponse_data**

```yaml Before
{
	"paymentUID": "string"
}

```

|**Name**|**Type**|**Description**|
| :- | :- | :- |
|paymentUID|string|Payment unique refrence ID|