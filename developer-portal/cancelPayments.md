---
title: Cancel a Payment
---

### **Cancel a Payment**

Finzly API allows user to cancel a payment (if it is permitted as per the cancellation rules). 

[PUT /payments/{paymentUID}/cancel](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/paymentapi/operation/cancelPayment/)

**HTTP Method: PUT**	

**Description-** Sending a PUT Request to "/payments/{paymentUID}/cancel" endpoint allows users to cancel a payment using the payment reference id. All the request parameters and objects are specified below -

**Request Parameters**


|**Name**|**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|paymentUID|path|string|true|Payment unique reference ID|

**JSON Response**

**Success Code - 200**

```yaml Before

{
  "status": "Success",
  "code": null
  "data": {
    "paymentUID": "<Payment UID>"
  }
}

```

|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|status|string|false|none|Status of the API request either it will be a success or a failure|
|code|string|false|none|Failure code associated with the failure status.|
|message|string|false|none|Error message corresponding to the error code indicating the issue in API call and an indication on how to resolve it.|
|data|CancelPaymentResponse_data|false|none|Payment Cancellation Response Data|


**CancelPaymentResponse_data**

```yaml Before
{
	"paymentUID": "string"
}

```

|**Name**|**Type**|**Description**|
| :- | :- | :- |
|paymentUID|string|Payment unique reference ID|