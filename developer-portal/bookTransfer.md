---
title: Book Transfer
---

## **Book Transfer**
Book transfers are used to move money within a bank or within a ledger. These transfers do not require
using any payment rail. 

[POST /v3/payments/booktransfer](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/booktransfer/)

**HTTP Method: POST**

**Description -** Sending a POST request to the  **/v3/payments/booktransfer** endpoint allows users to Initiate Book Transfer. All the request parameters and objects are specified below:

**Request Parameters**

All details will be passed in the body of the API request.

|**Name**|**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|body|body|[BookTransferRequest](https://apidocs.finzly.net/dashboard?javascript#schemabooktransferrequest)|true|Payment fields|

**JSON Response**

A successful POST request to this endpoint returns the following data

**Success Code - 200**

```yaml Before
{
  "status": "Success or Failure",
  "code": "BOOKTRF001 etc.",
  "message": "Failed to create a book transfer payment: ",
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



 **Book Transfer Request**:

|**Attribute**|**Type**|**Required**|**Restrictions**|**Notes**|
| :-: | :-: | :- | :- | :- | 
|externalReferenceId|string|TRUE|Max Limit – 50 chars |Unique reference id from a system outside of finzly. The external reference id can be used by the finzly for the request tracing (if needed) |
|senderAccount|[BookTransferSender](https://apidocs.finzly.net/dashboard#schemav3booktransfersender)|TRUE|Required|Sender account details|
|receiverAccount|[BookTransferReceiver](https://apidocs.finzly.net/dashboard#schemav3booktransferreceiver)|TRUE|Required|Receiver account details|
|paymentAmount|number|TRUE|Greater than Zero |Payment amount|
|paymentDate|string(date)|TRUE|Valid date format mm-dd-yyyy|Payment date in mm-dd-yyyy format|
|channel|string|FALSE|Valid channel such as API etc.|Channel associated with the payment. If not provided it will default to API|

 **Book Transfer Sender**

|**Attribute**|**Type**|**Required**|**Restrictions**|**Notes**|
| :-: | :-: | :- | :- | :- | 
|accountUID|string||FALSE|Valid account id exists in the system. Max Length 17 chars |Sender account unique identifier. If accountUID is provided then other attributes are not required such as accountNumber, accounttype, currency |
|accountNumber|string|FALSE| Valid account number |Sender account number|
|accountType|string|FALSE|DDA or GL|Account type|
|currency|string|FALSE|Valid 3-digit currency code such as USD |Sender Currency|

**Book Transfer Receiver**

|**Attribute**|**Type**|**Required**|**Restrictions**|**Notes**|
| :-: | :-: | :- | :-: | :-: |
|accountUID|string|FALSE|Valid account id exists in the system. Max Length 17 chars |Receiver account unique identifier. If accountUID is provided then other attributes are not required such as accountNumber, accounttype, currency|
|accountNumber|string|FALSE|none|Receiver account number|
|accountType|string|FALSE|DDA or GL|Account type|
|currency|string|FALSE|Valid 3-digit currency code such as USD|Sender Currency.|

 **Book Transfer Response:**

|**Attribute**|**Type**|**Required**|**Restrictions** |**Notes**|
| :-: | :- | :- | :- | :- |
|status|string |FALSE|Success or failure |Status of the API request either it will be a success or a failure|
|code|string|FALSE|Error code such as BOOK001 |Code associated with the error. |
|message|string |FALSE |none |Error message corresponding to the error code indicating the issue in API call and an indication on how to resolve it. |
|data|Book Transfer Response|FALSE |none|none|

 **Book Transfer Response**

|**Attribute**|**Type**|**Required**|**Restrictions**|**Notes**|
| :-: | :- | :- | :- | :-: |
|paymentUID|string|FALSE|none|Payment unique identifier.|
|externalReferenceId|string|FALSE|none|External reference id provided by the origination system|
|paymentStatus|String|FALASE|Valid Payment Status|Payment status|


