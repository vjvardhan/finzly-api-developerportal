---
title: Cancel Payment
---

### **Cancel a Payment**

You can cancel payments using this API as long as it has not been transmitted to the respective payment network.

[PUT /payments/{paymentUID}/cancel](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/paymentapi/operation/cancelPaymentV3/)

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