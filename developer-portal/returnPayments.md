---
title: Return Payments
---

### **Return a payment by paymentUID**
[PUT/payments/{paymentUID}/return](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/returnPaymentV3/)

**HTTP Method: PUT**

**Description -** Sending a PUT request to **/payments/{paymentUID}/return** endpoint allows users to return a payment. All the request parameters and objects are specified below

**Request Parameters**

In case of an incorrect transaction or refund, the users need to pass paymentUID in the API request path to return a payment.


|**Name**|**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|paymentUID|path|string|true|none|
|body|body|[ReturnPaymentRequest](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/returnPaymentV3/)|false |none|

JSON Response not available