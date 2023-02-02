---
title: Finzly Customer Account API
---

## **Bulk Payment**
Finzly system supports the ACH bulk payment processing in a NACHA format via FTP channel. The bank can create an FTP account to process the ACH bulk file in a Nacha format. The solution provided two types of FTP account.

**Following functions helps you to understand the current FX capabilities exposed via APIs**

### **Get Supported File Types**

[Get /bulkpayment/files/supportedFileType](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/getSupporedFileTypes/)

__HTTP Method: GET__

**Description** - Sending a GET request to the endpoint allows users to get supported files in a list format. 

**JSON Response**

A successful GET request to this endpoint returns the following data

**Response Code - 200**

```yaml Before
{
  "trasactionTypesList": [
    {
      "trasactionType": "NACHA, FEDWIRE, FINZLY-CSV",
      "fileType": ".csv or .txt etc"
    }
  ],
  "errors": {
    "code": "invalidMethod",
    "description": "Invalid HTTP method used"
  }
}

```
### **Get Bulk File Payment Details**

[GET/bulkpayment/files/{fileNumber}](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/getBulkFilePaymentDetails/)

**HTTP Method: GET**

**Description -** Sending a GET request to the **/bulkpayment/files/{fileNumber}** endpoint allows users to get bulk file payment details. The request parameters and objects are specified below- 

**Request Parameters**


|**Name** |**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|forexContractNo|path|string|true|none|

**JSON Response**

A successful GET request to this endpoint returns the following data

**Response Code - 200**

```yaml Before
{
  "fileNumber": 0,
  "fileName": "string",
  "fileDateTime": "string",
  "fileStatus": "string",
  "fileType": "string",
  "totalDebit": 0,
  "totalCredit": 0,
  "totalPayments": 0,
  "validPayments": 0,
  "errorPayments": 0,
  "creditMemoPostStatus": "string",
  "debitMemoPostStatus": "string",
  "counterparty": "string",
  "counterpartyId": 0,
  "paymentDate": "2019-08-24",
  "channel": "string",
  "possibleUserAction": [
    {
      "id": "Approved or Rejected etc",
      "displayName": "APPROVED / REJECTED etc",
      "errors": {
        "code": "invalidMethod",
        "description": "Invalid HTTP method used"
      }
    }
  ],
  "paymentBatches": [
    {
      "batchId": "string",
      "totalBatchDebit": 0,
      "totalBatchCredit": 0,
      "batchCurrency": "string",
      "secCode": "PPD, CCD etc",
      "status": "VALIDATED or ERROR",
      "transactions": [
        {
          "paymentId": 0,
          "transactionType": "string",
          "amount": 0,
          "currency": "string",
          "deliveryMethod": "ACH",
          "createdBy": "string",
          "paymentType": "string",
          "paymentDate": "2019-08-24",
          "paymentStatus": "string",
          "settlementDate": "2019-08-24",
          "lastUpdatedBy": "string",
          "creationDateTime": "string",
          "lastUpdatedTime": "string",
          "receiverName": "string",
          "receiverAccountNumber": "string",
          "senderAccountNumber": "string"
        }
      ]
    }
  ],
  "messages": {
    "uploadErrors": [
      {
        "bulkFileId": 0,
        "fileNumber": 0,
        "validationCode": "string",
        "displayMessage": "string",
        "validationType": "string",
        "creationDateTime": "string",
        "approvedBy": "string",
        "approvedDateTime": "string"
      }
    ],
    "uploadWarnings": [
      {
        "bulkFileId": 0,
        "fileNumber": 0,
        "validationCode": "string",
        "displayMessage": "string",
        "validationType": "string",
        "creationDateTime": "string",
        "approvedBy": "string",
        "approvedDateTime": "string"
      }
    ]
  },
  "errors": {
    "code": "invalidMethod",
    "description": "Invalid HTTP method used"
  }
}

```

|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|fileNumber|integer|false|none|none|
|fileName|string|false|none|none|
|fileDateTime|string(dateTime)|false|none|none|
|fileStatus|string|false|none|none|
|fileType|string|false|none|none|
|totalDebit|number(double)|false|none|none|
|totalCredit|number(double)|false|none|none|
|totalPayments|number(integer)|false|none|none|
|validPayments|number(integer)|false|none|none|
|errorPayments|number(integer)|false|none|none|
|creditMemoPostStatus|string|false|none|none|
|debitMemoPostStatus|string|false|none|none|
|counterparty|string|false|none|none|
|counterpartyId|integer|false|none|none|
|paymentDate|string(date)|false|none|Payment date in mm/dd/yyyy format|
|channel|string|false|none|none|
|possibleUserAction|[[BulkfileActions](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/getBulkFilePaymentDetails/)]|false|none|none|
|paymentBatches|<p>[[BulkPaymentBatches](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/getBulkFilePaymentDetails/)]</p><p></p><p></p>|false|none|none|
|messages|[BulkFile_messages](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/getBulkFilePaymentDetails/)|false|none|none|
|errors|<p>[Error](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/getBulkFilePaymentDetails/)</p><p></p>|false|none|none|

**Bulk File Actions**

```yaml Before
{
  "id": "Approved or Rejected etc",
  "displayName": "APPROVED / REJECTED etc",
  "errors": {
    "code": "invalidMethod",
    "description": "Invalid HTTP method used"
  }
}

```

|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|id|string|false|none|none|
|displayName|string|false|none|none|
|errors|[Error](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/getBulkFilePaymentDetails/)|false|none|none|

**Error**


|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|code|string|false|none|Error code assigned by the system|
|description|string|false|none|Error description to provide additional details about the error code|

**Bulk Payment Batches**

```yaml Before
{
  "batchId": "string",
  "totalBatchDebit": 0,
  "totalBatchCredit": 0,
  "batchCurrency": "string",
  "secCode": "PPD, CCD etc",
  "status": "VALIDATED or ERROR",
  "transactions": [
    {
      "paymentId": 0,
      "transactionType": "string",
      "amount": 0,
      "currency": "string",
      "deliveryMethod": "ACH",
      "createdBy": "string",
      "paymentType": "string",
      "paymentDate": "2019-08-24",
      "paymentStatus": "string",
      "settlementDate": "2019-08-24",
      "lastUpdatedBy": "string",
      "creationDateTime": "string",
      "lastUpdatedTime": "string",
      "receiverName": "string",
      "receiverAccountNumber": "string",
      "senderAccountNumber": "string"
    }
  ]
}

```
|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|batchId|string|false|none|none|
|totalBatchDebit|number(double)|false|none|none|
|totalBatchCredit|number(double)|false|none|none|
|batchCurrency|string|false|none|none|
|secCode|string|false|none|none|
|status|string|false|none|none|
|transactions|[[BulkTransaction](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/getBulkFilePaymentDetails/)]|false|none|none|

**Bulk Transaction**

```yaml Before
{
  "paymentId": 0,
  "transactionType": "string",
  "amount": 0,
  "currency": "string",
  "deliveryMethod": "ACH",
  "createdBy": "string",
  "paymentType": "string",
  "paymentDate": "2019-08-24",
  "paymentStatus": "string",
  "settlementDate": "2019-08-24",
  "lastUpdatedBy": "string",
  "creationDateTime": "string",
  "lastUpdatedTime": "string",
  "receiverName": "string",
  "receiverAccountNumber": "string",
  "senderAccountNumber": "string"
}

```



|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|paymentId|number|false|none|none|
|transactionType|string|false|none|none|
|amount|number(double)|false|none|none|
|currency|string|false|none|none|
|deliveryMethod|string|false|none|none|
|createdBy|string|false|none|none|
|paymentType|string|false|none|none|
|paymentDate|string(date)|false|none|Payment date in mm/dd/yyyy format|
|paymentStatus|string|false|none|none|
|settlementDate|string(date)|false|none|Settlement date in mm/dd/yyyy format|
|lastUpdatedBy|string|false|none|none|
|lastUpdatedTime|string(datetime)|false|none|none|
|receiverName|string|false|none|none|
|receiverAccountNumber|string|false|none|none|
|senderAccountNumber|string|false|none|none|

**Bulk File Messages**


|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|uploadErrors|[[UploadMessages](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/getBulkFilePaymentDetails/)]|false|none|none|
|uploadWarnings|<p>[[UploadMessages](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/getBulkFilePaymentDetails/)]</p><p></p>|false|none|none|

**Upload Messages**
```yaml Before
{
  "bulkFileId": 0,
  "fileNumber": 0,
  "validationCode": "string",
  "displayMessage": "string",
  "validationType": "string",
  "creationDateTime": "string",
  "approvedBy": "string",
  "approvedDateTime": "string"
}


```

|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|bulkFileId|integer|false|none|none|
|fileNumber|integer|false|none|none|
|validationCode|string|false|none|none|
|displayMessage|string|false|none|none|
|validationType|string|false|none|none|
|creationDateTime|string(datetime)|false|none|none|
|approvedBy|string|false|none|none|
|approvedDateTime|string(datetime)|false|none|none|

**Error**

```yaml Before
{
  "code": "invalidMethod",
  "description": "Invalid HTTP method used"
}

```

|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|code|string|false|none|Error code assigned by the system|
|description|string|false|none|Error description to provide additional details about the error code|

### **Upload Bulk Files**
[POST /bulkpayment/files](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/uploadBulkFiles/)

**HTTP Method: POST**

**Description -** Sending a POST request to /bulkpayment/files allows users to Upload files for bulk payment. The request parameters and objects are specified below- 

**Request Parameters**

|**Name** |**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|body|body|[BulkFilesRequest](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/uploadBulkFiles/)|false|none|
**JSON Response**

**A successful POST request to this endpoint returns the following data -**

**Response Code - 200**
```yaml Before
{
  "bulkUploadedFiles": [
    {
      "fileNumber": 0,
      "fileName": "string",
      "fileDateTime": "string",
      "fileStatus": "string",
      "fileType": "string",
      "totalDebit": 0,
      "totalCredit": 0,
      "totalPayments": 0,
      "validPayments": 0,
      "errorPayments": 0,
      "creditMemoPostStatus": "string",
      "debitMemoPostStatus": "string",
      "counterparty": "string",
      "counterpartyId": 0,
      "paymentDate": "2019-08-24",
      "channel": "string",
      "possibleUserAction": [
        {
          "id": "Approved or Rejected etc",
          "displayName": "APPROVED / REJECTED etc",
          "errors": {
            "code": "invalidMethod",
            "description": "Invalid HTTP method used"
          }
        }
      ],
      "paymentBatches": [
        {
          "batchId": "string",
          "totalBatchDebit": 0,
          "totalBatchCredit": 0,
          "batchCurrency": "string",
          "secCode": "PPD, CCD etc",
          "status": "VALIDATED or ERROR",
          "transactions": [
            {
              "paymentId": 0,
              "transactionType": "string",
              "amount": 0,
              "currency": "string",
              "deliveryMethod": "ACH",
              "createdBy": "string",
              "paymentType": "string",
              "paymentDate": "2019-08-24",
              "paymentStatus": "string",
              "settlementDate": "2019-08-24",
              "lastUpdatedBy": "string",
              "creationDateTime": "string",
              "lastUpdatedTime": "string",
              "receiverName": "string",
              "receiverAccountNumber": "string",
              "senderAccountNumber": "string"
            }
          ]
        }
      ],
      "messages": {
        "uploadErrors": [
          {
            "bulkFileId": 0,
            "fileNumber": 0,
            "validationCode": "string",
            "displayMessage": "string",
            "validationType": "string",
            "creationDateTime": "string",
            "approvedBy": "string",
            "approvedDateTime": "string"
          }
        ],
        "uploadWarnings": [
          {
            "bulkFileId": 0,
            "fileNumber": 0,
            "validationCode": "string",
            "displayMessage": "string",
            "validationType": "string",
            "creationDateTime": "string",
            "approvedBy": "string",
            "approvedDateTime": "string"
          }
        ]
      },
      "errors": {
        "code": "invalidMethod",
        "description": "Invalid HTTP method used"
      }
    }
  ],
  "errors": {
    "code": "invalidMethod",
    "description": "Invalid HTTP method used"
  },
  "pagination": {
    "totalRecords": 100,
    "returnedRecords": 10,
    "pageReturned": 2,
    "pageSize": 10
  }
}

```
|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|bulkUploadedFiles|<p>[[BulkFile](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/uploadBulkFiles/)]</p><p></p>|false|none|none|
|errors|[Error](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/uploadBulkFiles/)|false|none|none|
|pagination|[Pagination](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/uploadBulkFiles/)|false|none|none|


**Bulk File**
```yaml Before
{
  "fileNumber": 0,
  "fileName": "string",
  "fileDateTime": "string",
  "fileStatus": "string",
  "fileType": "string",
  "totalDebit": 0,
  "totalCredit": 0,
  "totalPayments": 0,
  "validPayments": 0,
  "errorPayments": 0,
  "creditMemoPostStatus": "string",
  "debitMemoPostStatus": "string",
  "counterparty": "string",
  "counterpartyId": 0,
  "paymentDate": "2019-08-24",
  "channel": "string",
  "possibleUserAction": [
    {
      "id": "Approved or Rejected etc",
      "displayName": "APPROVED / REJECTED etc",
      "errors": {
        "code": "invalidMethod",
        "description": "Invalid HTTP method used"
      }
    }
  ],
  "paymentBatches": [
    {
      "batchId": "string",
      "totalBatchDebit": 0,
      "totalBatchCredit": 0,
      "batchCurrency": "string",
      "secCode": "PPD, CCD etc",
      "status": "VALIDATED or ERROR",
      "transactions": [
        {
          "paymentId": 0,
          "transactionType": "string",
          "amount": 0,
          "currency": "string",
          "deliveryMethod": "ACH",
          "createdBy": "string",
          "paymentType": "string",
          "paymentDate": "2019-08-24",
          "paymentStatus": "string",
          "settlementDate": "2019-08-24",
          "lastUpdatedBy": "string",
          "creationDateTime": "string",
          "lastUpdatedTime": "string",
          "receiverName": "string",
          "receiverAccountNumber": "string",
          "senderAccountNumber": "string"
        }
      ]
    }
  ],
  "messages": {
    "uploadErrors": [
      {
        "bulkFileId": 0,
        "fileNumber": 0,
        "validationCode": "string",
        "displayMessage": "string",
        "validationType": "string",
        "creationDateTime": "string",
        "approvedBy": "string",
        "approvedDateTime": "string"
      }
    ],
    "uploadWarnings": [
      {
        "bulkFileId": 0,
        "fileNumber": 0,
        "validationCode": "string",
        "displayMessage": "string",
        "validationType": "string",
        "creationDateTime": "string",
        "approvedBy": "string",
        "approvedDateTime": "string"
      }
    ]
  },
  "errors": {
    "code": "invalidMethod",
    "description": "Invalid HTTP method used"
  }
}

```
**Data Returned Objects**


|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|fileNumber|integer|false|none|none|
|fileName|string|false|none|none|
|fileDateTime|string(datetime)|false|none|none|
|fileStatus|string|false|none|none|
|fileType|string|false|none|none|
|totalDebit|number(double)|false|none|none|
|totalCredit|number(double)|false|none|none|
|totalPayments|number(double)|false|none|none|
|validPayments|number(integer)|false|none|none|
|errorPayments|number(integer)|false|none|none|
|creditMemoPostStatus|string|false|none|none|
|debitMemoPostStatus|string|false|none|none|
|counterparty|string|false|none|none|
|counterpartyId|integer|false|none|none|
|paymentDate|string(date)|false|none|Payment date in mm/dd/yyyy format|
|channel|string|false|none|none|
|possibleUserAction|[[BulkfileActions](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/uploadBulkFiles/)]|false|none|none|
|paymentBatches|[[BulkPaymentBatches](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/uploadBulkFiles/)]|false|none|none|
|messages|[BulkFile_messages](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/uploadBulkFiles/)|false|none|none|
|errors|[Error](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/uploadBulkFiles/)|false|none|none|

```yaml Before
{
  "code": "invalidMethod",
  "description": "Invalid HTTP method used"
}

```
|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|code|string|false|none|Error code assigned by the system|
|description|string|false|none|Error description to provide addtional details about the error code|



**Pagination**

```yaml Before
{
  "totalRecords": 100,
  "returnedRecords": 10,
  "pageReturned": 2,
  "pageSize": 10
}

```

|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|totalRecords|number(integer)|false|none|Total number of records exist in the system for a given filter|
|returnedRecords|number(integer)|false|none|Total number of records returned|
|pageReturned|number(integer)|false|none|Current number of page returned|
|pageSize|number(integer)|false|none|Total number of records in a given pages|

### **Get Bulk Files**
[POST /bulkpayment/files/search](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/getBulkFiles/)

**HTTP Method: POST**

Description - Sending a POST request to **/bulkpayment/files/search** allows users to search all files based on CounterParty (and Payment Date criteria). The request parameters and objects are specified below - 

**Request Parameters**


|**Name** |**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|body|body|[BulkFilesRequest](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/getBulkFiles/)|false|none|


**JSON Response**

**A successful POST request to this endpoint returns the following data -**

**Response Code - 200**

```yaml Before

{
  "bulkUploadedFiles": [
    {
      "fileNumber": 0,
      "fileName": "string",
      "fileDateTime": "string",
      "fileStatus": "string",
      "fileType": "string",
      "totalDebit": 0,
      "totalCredit": 0,
      "totalPayments": 0,
      "validPayments": 0,
      "errorPayments": 0,
      "creditMemoPostStatus": "string",
      "debitMemoPostStatus": "string",
      "counterparty": "string",
      "counterpartyId": 0,
      "paymentDate": "2019-08-24",
      "channel": "string",
      "possibleUserAction": [
        {
          "id": "Approved or Rejected etc",
          "displayName": "APPROVED / REJECTED etc",
          "errors": {
            "code": "invalidMethod",
            "description": "Invalid HTTP method used"
          }
        }
      ],
      "paymentBatches": [
        {
          "batchId": "string",
          "totalBatchDebit": 0,
          "totalBatchCredit": 0,
          "batchCurrency": "string",
          "secCode": "PPD, CCD etc",
          "status": "VALIDATED or ERROR",
          "transactions": [
            {
              "paymentId": 0,
              "transactionType": "string",
              "amount": 0,
              "currency": "string",
              "deliveryMethod": "ACH",
              "createdBy": "string",
              "paymentType": "string",
              "paymentDate": "2019-08-24",
              "paymentStatus": "string",
              "settlementDate": "2019-08-24",
              "lastUpdatedBy": "string",
              "creationDateTime": "string",
              "lastUpdatedTime": "string",
              "receiverName": "string",
              "receiverAccountNumber": "string",
              "senderAccountNumber": "string"
            }
          ]
        }
      ],
      "messages": {
        "uploadErrors": [
          {
            "bulkFileId": 0,
            "fileNumber": 0,
            "validationCode": "string",
            "displayMessage": "string",
            "validationType": "string",
            "creationDateTime": "string",
            "approvedBy": "string",
            "approvedDateTime": "string"
          }
        ],
        "uploadWarnings": [
          {
            "bulkFileId": 0,
            "fileNumber": 0,
            "validationCode": "string",
            "displayMessage": "string",
            "validationType": "string",
            "creationDateTime": "string",
            "approvedBy": "string",
            "approvedDateTime": "string"
          }
        ]
      },
      "errors": {
        "code": "invalidMethod",
        "description": "Invalid HTTP method used"
      }
    }
  ],
  "errors": {
    "code": "invalidMethod",
    "description": "Invalid HTTP method used"
  },
  "pagination": {
    "totalRecords": 100,
    "returnedRecords": 10,
    "pageReturned": 2,
    "pageSize": 10
  }
}

```

|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|bulkUploadedFiles|<p>[[BulkFile](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/getBulkFiles/)]</p><p></p>|false|none|none|
|errors|[Error](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/getBulkFiles/)|false|none|none|
|pagination|[Pagination](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/getBulkFiles/)|false|none|none|
### **Approve File**
[PUT /bulkpayment/files/{fileNumber}/approve](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/approveFile/)

**HTTP Method: PUT**

**Description -** Sending a PUT request to **PUT /bulkpayment/files/{fileNumber}/approve** endpoint allows users to approve bulk payment files by using file number. The request parameters and objects are specified below - 

**Request Parameters**

The fileNumber must be passed in the path of API request.

|**Name** |**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|fileNumber|path|string|true|none|

**JSON Response(JSON schema NA in the API doc provided by the client)**

**A successful PUT request to this endpoint returns the following data -**

**Response Code - 200**

### **Reject File**
[PUT /bulkpayment/files/{fileNumber}/reject](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/rejectFile/)

**HTTP Method: PUT**

**Description -** Sending a PUT request to the **bulkpayment/files/{fileNumber}/reject** endpoint allows users to reject Bulk Payment File. The request parameters and objects are specified below - 

**Request Parameters**

The fileNumber must be passed in the path of API request.

|**Name** |**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|fileNumber|path|string|true|none|

**JSON Response(JSON schema NA in the API doc provided by the client)**

**A successful PUT request to this endpoint returns the following data -**

**Response Code - 200**
