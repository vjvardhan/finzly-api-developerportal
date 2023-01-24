---
title: Finzly Customer Account API
---

## Payment Origination
Payments APIs enable third parties, banks, and downstream partners to initiate and manage customer payments.

The single payment API supports the payment origination for the various payment rails such as ACH, FedWire, SWIFT, and Instant Payments based on speed preference.

The following use cases help you to understand the current payment capabilities exposed via APIs.

1. Search Payments 
2. Create Credit Payment
3. Create Debit Payment

## **Supported Customer Accounts API functions**

### **Search Payments**

[POST /v3/payments/search](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/searchPaymentsV3/)

**HTTP  Method: GET**

**Description -** Sending a GET request to /v3/payments/search endpoint allows users to retrieve a list of payments. All the request parameters and objects are specified below:

**Request Parameters**

No argument is required. Only payment details will be passed in the body of the API request.


|**Name**|**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|body|body|[PaymentSearch](https://apidocs.finzly.net/dashboard?http=#schemapaymentsearch)|false|none|

**JSON Response**


```yaml Before

{
  "status": "Success or Failure",
  "code": "PAYMENT001 etc.",
  "message": "Failed to search a payment: ",
  "data": [
    {
      "paymentUID": 12341,
      "counterPartyId": "string",
      "senderUID": "string",
      "senderAccountNumber": "string",
      "senderAccountName": "string",
      "senderName": "string",
      "senderAccountType": "string",
      "ultimateSenderName": "string",
      "ultimateSenderAccountNumber": "string",
      "ultimateSenderAddress1": "string",
      "ultimateSenderAddress2": "string",
      "ultimateSenderTaxId": "string",
      "ultimateSenderCity": "string",
      "ultimateSenderState": "string",
      "ultimateSenderZip": "string",
      "ultimateSenderCountry": "string",
      "beneficiaryUID": "string",
      "beneficiaryName": "string",
      "senderAmount": "string",
      "paymentDate": "string",
      "receiverCurrency": "string",
      "senderCurrency": "string",
      "receiverAmount": 0,
      "deliveryMethod": "ACH",
      "receiverAccountNumber": "string",
      "ultimateReceiverName": "string",
      "ultimateReceiverAccountNumber": "string",
      "ultimateReceiverAddress1": "string",
      "ultimateReceiverAddress2": "string",
      "ultimateReceiverTaxId": "string",
      "ultimateReceiverCity": "string",
      "ultimateReceiverState": "string",
      "ultimateReceiverZip": "string",
      "ultimateReceiverCountry": "string",
      "createdBy": "string",
      "bankFeePayer": "remitter",
      "paymentNotes": "payment for invoice ABC123",
      "forexContract": "1325",
      "occurrences": {
        "frequency": "Daily",
        "startDate": "2020-01-01",
        "payUntil": "Cancelled",
        "endDate": "2020-01-29",
        "numberOfPayments": 10,
        "status": "Active"
      },
      "status": "FUTURE_DATED",
      "displayStatus": "Scheduled",
      "notification": {
        "emailAddress": "me@gmail.com",
        "phoneNumber": "111223333 or 111-22-3333",
        "message": "Payment to XXX"
      },
      "audit": {
        "submitterId": "1234567",
        "submissionDate": "3-3-2020",
        "approvers": [
          {
            "approverId": "12345",
            "approvedDate": "3-3-2020"
          }
        ]
      },
      "creationDateTime": "string",
      "customerType": "Corporate or Consumer",
      "deliveryAgentType": "string",
      "quoteId": "string",
      "wireType": "string",
      "counterParty": "string",
      "businessUnit": "string",
      "channel": "string",
      "costCenter": "string",
      "book": "string",
      "businessUnitId": "string"
    }
  ]
}

```

|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|status|string|false|none|Status of the API request either it will be a success or a failure|
|code|string|false|none|Code associated with the error.|
|message|string|false|none|Error message corresponding to the error code indicating the issue in API call and an indication on how to resolve it.|
|data|[Payment]|false|none|none|

### **Create Credit Payment**
[POST /v3/payments/creditrequest](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/createCreditPaymentV3/)

**HTTP Method: POST**

**Description -** Sending a POST request to **/v3/payments/creditrequest** endpoint allows users to submit domestic or international one time or recurring payments. All the request parameters and objects are specified below:

**Request Parameters**

All details of the users to which we want to make the payment will be passed in the body of the API request.


|**Name**|**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|body|body|[CreditPaymentRequest](https://apidocs.finzly.net/dashboard?java=#schemacreditpaymentrequest)|true|Payment fields|


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
|data|[BookTransferResponse_data](https://apidocs.finzly.net/dashboard?java=#schemabooktransferresponse_data)|false|none|none|

**Book Transfer Response Data**
```yaml Before
{
  "paymentUID": "string",
  "paymentStatus": "string",
  "externalReferenceId": "string"
}
```

|Name|Type|Required|Restrictions|Description|
| :- | :- | :- | :- | :- |
|paymentUID|string|false|none|none|
|paymentStatus|string|false|none|none|
|externalReferenceId|string|false|none|none|

### **Create Debit Payment**
[POST /v3/payments/debitrequest](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/createDebitPaymentV3/)

**HTTP Method: POST**

**Description -** Sending a POST request to /v3/payments/debitrequest endpoint allows users to submit domestic or international one time or recurring payments. All the request parameters and objects are specified below:

**Request Parameters**

All details of the users from which want to receive the payment will be passed in the body of the API request.


|**Name**|**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|body|body|[DebitPaymentRequest](https://apidocs.finzly.net/dashboard?java=#schemadebitpaymentrequest)|true|Payment fields|

**JSON Response**

A successful POST request to this endpoint returns the following data -

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
|data|[BookTransferResponse_data](https://apidocs.finzly.net/dashboard?java=#schemabooktransferresponse_data)|false|none|none|

### **Get Payment by UIDV3**
[GET /v3/payments/{paymentUID}](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/getPaymentByUIDV3/)

**HTTP Method: GET**

**Description -** Sending a GET Request to /v3/payments/{paymentUID} endpoint allows users to retrieve  payment details using payment uid **in the path of the API request**. All the request parameters and objects are specified below:


**Request Parameters**

|**Name**|**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|paymentUID|path|string|true|none|

**JSON Response**

A successful GET request to this endpoint returns the following data -

**Success Code - 200**

```yaml Before
{
  "status": "Success or Failure",
  "code": "PAYMENT001 etc.",
  "message": "Failed to retrieve a payment: ",
  "data": {
    "paymentUID": 12341,
    "counterPartyId": "string",
    "senderUID": "string",
    "senderAccountNumber": "string",
    "senderAccountName": "string",
    "senderName": "string",
    "senderAccountType": "string",
    "ultimateSenderName": "string",
    "ultimateSenderAccountNumber": "string",
    "ultimateSenderAddress1": "string",
    "ultimateSenderAddress2": "string",
    "ultimateSenderTaxId": "string",
    "ultimateSenderCity": "string",
    "ultimateSenderState": "string",
    "ultimateSenderZip": "string",
    "ultimateSenderCountry": "string",
    "beneficiaryUID": "string",
    "beneficiaryName": "string",
    "senderAmount": "string",
    "paymentDate": "string",
    "receiverCurrency": "string",
    "senderCurrency": "string",
    "receiverAmount": 0,
    "deliveryMethod": "ACH",
    "receiverAccountNumber": "string",
    "ultimateReceiverName": "string",
    "ultimateReceiverAccountNumber": "string",
    "ultimateReceiverAddress1": "string",
    "ultimateReceiverAddress2": "string",
    "ultimateReceiverTaxId": "string",
    "ultimateReceiverCity": "string",
    "ultimateReceiverState": "string",
    "ultimateReceiverZip": "string",
    "ultimateReceiverCountry": "string",
    "createdBy": "string",
    "bankFeePayer": "remitter",
    "paymentNotes": "payment for invoice ABC123",
    "forexContract": "1325",
    "occurrences": {
      "frequency": "Daily",
      "startDate": "2020-01-01",
      "payUntil": "Cancelled",
      "endDate": "2020-01-29",
      "numberOfPayments": 10,
      "status": "Active"
    },
    "status": "FUTURE_DATED",
    "displayStatus": "Scheduled",
    "notification": {
      "emailAddress": "me@gmail.com",
      "phoneNumber": "111223333 or 111-22-3333",
      "message": "Payment to XXX"
    },
    "audit": {
      "submitterId": "1234567",
      "submissionDate": "3-3-2020",
      "approvers": [
        {
          "approverId": "12345",
          "approvedDate": "3-3-2020"
        }
      ]
    },
    "creationDateTime": "string",
    "customerType": "Corporate or Consumer",
    "deliveryAgentType": "string",
    "quoteId": "string",
    "wireType": "string",
    "counterParty": "string",
    "businessUnit": "string",
    "channel": "string",
    "costCenter": "string",
    "book": "string",
    "businessUnitId": "string"
  }
}

```

|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|status|string|false|none|Status of the API request either it will be a success or a failure|
|code|string|false|none|Code associated with the error.|
|message|string|false|none|Error message corresponding to the error code indicating the issue in API call and an indication on how to resolve it.|
|data|[Payment](https://apidocs.finzly.net/dashboard?java=#schemapayment)|false|none|none|

### **Cancel Payment by paymentUID (v3)**


[PUT /v3/payments/{paymentUID}/cancel](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/cancelPaymentV3/)

**HTTP Method: PUT**	

**Description-** Sending a PUT Request to /v3/payments/{paymentUID}/cancel endpoint allows users to cancel a payment.using paymentUID. All the request parameters and objects are specified below -



|**Name**|**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|paymentUID|path|string|true|none|

**JSON Response**

A successful PUT request to this endpoint returns the following data 

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
|data|[CancelPaymentResponse_data](https://apidocs.finzly.net/dashboard?java=#schemacancelpaymentresponse_data)|false|none|none|

Cancel Payment Response data
```yaml Before
{
  "paymentUID": "string"
}

```

|**Name**|**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|paymentUID|string|false|none|none|

### **Return a payment by paymentUID (v3)**
[PUT/v3/payments/{paymentUID}/return](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/returnPaymentV3/)

**HTTP Method: PUT**

**Description -** Sending a PUT request to /v3/payments/{paymentUID}/return endpoint allows users to return a payment. All the request parameters and objects are specified below

**Request Parameters**

In case of an incorrect transaction or refund, the users need to pass paymentUID in the API request path to return a payment.


|**Name**|**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|paymentUID|path|string|true|none|
|body|body|[ReturnPaymentRequest](https://apidocs.finzly.net/dashboard?java=#schemareturnpaymentrequest)|false |none|

JSON Response not available
### **Reverse Payment by paymentUID (v3)**
[PUT /v3/payments/{paymentUID}/reverse](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/reversePaymentV3/)

**HTTP Method: PUT**

**Description -** Sending a PUT request to /v3/payments/{paymentUID}/reverse endpoint allows users to reverse a payment. All the request parameters and objects are specified below

**Request Parameters**


|**Name**|**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|paymentUID|path|string|true|none|
|body|body|[ReversePaymentRequest](https://apidocs.finzly.net/dashboard?java=#schemareversepaymentrequest)|false |none|

**JSON Response not available**

