---
title: Search Payments
---

### **Search Payments**

[POST /payments/search](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/searchPaymentsV3/)

**HTTP  Method: GET**

**Description -** Sending a GET request to **/payments/search** endpoint allows users to retrieve a list of payments. All the request parameters and objects are specified below:

**Request Parameters**

No argument is required. Only payment details will be passed in the body of the API request.


|**Name**|**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|body|body|[PaymentSearch](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/searchPaymentsV3/)|false|none|

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

### **Get Payment by UID**
[GET /payments/{paymentUID}](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/getPaymentByUIDV3/)

**HTTP Method: GET**

**Description -** Sending a GET Request to **/payments/{paymentUID}** endpoint allows users to retrieve  payment details using payment uid in the path of the API request. All the request parameters and objects are specified below:


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
|data|[Payment](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/getPaymentByUIDV3/)|false|none|none|