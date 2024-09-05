---
title: Finzly Customer Account API
---

## **Positive Pay**
Payments Positive Pay has two sets of APIs.

Positive Pay Rules APIs enable third parties, bank customers, and downstream partners to define positive rules to monitor ACH debits, set up Fedwire drawdown requests, and "request for pay - RFP" rules for instant payments.

Positive Pay Decision APIs approve or reject the exceptions identified by the positive pay rules engine.

## **API Functions**
### **Search Positive Pay Rules**

[POST /positivepay/rules/search](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/searchPositivePayRules%20(/)/)

**HTTP Method: POST**

**Description -** Sending a POST request to **/positivepay/rules/search** allows users to search positive pay rules for the given criteria. All the request parameters and objects are specified below


|Name |In|Type|Required|Description|
| :- | :- | :- | :- | :- |
|body|body|[ReversePaymentRequest](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/searchPositivePayRules%20(/)/)|false |none|


**JSON Response**

A successful POST request to this endpoint returns the following data

**Response Code - 200**

```yaml Before
{
  "status": "Success or Failure",
  "code": "PP001 etc.",
  "message": "Failed to get positive rules: ",
  "data": [
    {
      "ruleUID": 123456789,
      "paymentRuleType": "ACH, FEDWIRE, RFP",
      "customerName": "ABC Company",
      "customerAccountNumber": "12387878",
      "achCompanyID": 122334789,
      "beneBankId": "12345678",
      "beneName": "XYZ Name",
      "beneBankName": "Bank Name",
      "beneAccountNumber": "12345678",
      "amount": 10,
      "currency": "USD",
      "amountType": "Exact or Maximum",
      "frequency": "Onetime, Weekly etc.",
      "secCode": "CCD, PPD etc.",
      "status": "Active, Expired",
      "effectiveDate": "0016-07-14",
      "expiryDate": "0016-07-14"
    }
  ]
}

```
|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|status|string|false|none|Status of the API request either it will be a success or a failure|
|code|string|false|none|Code associated with the error.|
|message|string|false|none|Error message corresponding to the error code indicating the issue in API call and an indication on how to resolve it.|
|data|[[PositivePayRule](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/searchPositivePayRules%20(/)/)]|false|none|none|

**Positive Pay Rule**


|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|ruleUID|number(int64)|false|none|Positive rule unique reference id|
|paymentRuleType|string|false|none|Payment type associated with the rule such as ACH for Positive Pay, FEDWIRE for Drawdown, RTP for Request for Pay etc.|
|customerName|string|false|none|Customer name associated with the payment positive rule|
|customerAccountNumber|string|false|none|Bank Account Number|
|achCompanyID|number|false|none|ACH company ID is a 10-digit identifier used by banks and Nacha, the operator of the ACH network, to identify the entity collecting payments or sending money via ACH (also referred to as an “originator”)|
|beneBankId|string|false|none|Bank unique id that is used to identify a specific bank|
|beneName|string|false|none|A beneficiary is the person or entity that will receive the payment|
|beneBankName|string|false|none|Beneficiary bank name|
|beneAccountNumber|string|false|none|A beneficiary bank account number|
|amount|number|false|none|Payment amount|
|currency|string|false|none|Currency Code|
|amountType|string|false|none|Type of amount associated with the positive pay rule.|
|frequency|string|false|none|Positive pay rule frequency|
|secCode|string|false|none|SEC code associated with the ACH positive rule|
|status|string|false|none|Current state of the rule whether Active or Expired etc.|
|effectiveDate|string(date)|false|none|Rule effective date in mm-dd-yyyy format|
|expiryDate|string(date)|false|none|Rule effective date in mm-dd-yyyy format|


### **Update Positive Pay Rules**
[PUT /positivepay/rules](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/updateRules/)

**HTTP Method: PUT**

**Description -** Sending a PUT request to **/positivepay/rules** endpoint allows users to update Positive Pay Rule.  All the request parameters and objects are specified below

**Request Parameters**

|**Name** |**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|body|body|[PositivePayRule](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/updateRules/)|false |none|


**JSON Response**

A successful PUT request to this endpoint returns the following data -

**Response Code - 200**

```yaml Before
{
  "status": "Success or Failure",
  "code": "PP001 etc.",
  "message": "Failed to update a positive rule: .",
  "ruleUID": 123456789
}

```

|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|status|string|false|none|This will return Success/Failed|
|code|string|false|none|This will indicate the error code in case of API error|
|message|string|false|none|This will be the detailed error message indicating what failed and how to fix the issue|
|ruleUID|number(int64)|false|none|Positive rule unique id|


### **Add PositivePay Rule**
[POST /positivepay/rules](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/addPositiveRules/)

**HTTP Method: POST**

**Description -**  Sending a PUT request to the **/positivepay/rules** endpoint allows users to add a positive pay rule. All the request parameters and objects are specified below- 

**Request Parameters**


|**Name** |**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|body|body|<p>[AddPositivePayRule](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/addPositiveRules/)</p><p></p>|false |none|

**JSON Response**

A successful POST request to this endpoint returns the following data

**Response Code - 200**

```yaml Before
{
  "status": "Success or Failure",
  "code": "PP001 etc.",
  "message": "Failed to add a positive rule: .",
  "ruleUID": 123456789
}

```

|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|status|string|false|none|This will return Success/Failed|
|code|string|false|none|This will indicate the error code in case of API error|
|message|string|false|none|This will be the detailed error message indicating what failed and how to fix the issue|
|ruleUID|number(int64)|false|none|Positive rule unique id|

### **Get PositivePay Rule By RuleUID**
[GET /positivepay/rules/{ruleUID}](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/getPostivePayRule/)

**HTTP Method - GET**

**Description -** Sending a GET request to the **/positivepay/rules/{ruleUID}** endpoint allows users to get PositivePay Rule by providing ruleUID in the path of the API request.  All the request parameters and objects are specified below- 

**Request Parameters**


|Name |In|Type|Required|Description|
| :- | :- | :- | :- | :- |
|ruleUID|path|string|true|Positive Pay Rule unique id|

**JSON Response**

A successful GET request to this endpoint returns the following data

**Response Code - 200**

```yaml Before

{
  "status": "Success or Failure",
  "code": "PP001 etc.",
  "message": "Failed to get positive rule: ",
  "data": {
    "ruleUID": 123456789,
    "paymentRuleType": "ACH, FEDWIRE, RFP",
    "customerName": "ABC Company",
    "customerAccountNumber": "12387878",
    "achCompanyID": 122334789,
    "beneBankId": "12345678",
    "beneName": "XYZ Name",
    "beneBankName": "Bank Name",
    "beneAccountNumber": "12345678",
    "amount": 10,
    "currency": "USD",
    "amountType": "Exact or Maximum",
    "frequency": "Onetime, Weekly etc.",
    "secCode": "CCD, PPD etc.",
    "status": "Active, Expired",
    "effectiveDate": "0016-07-14",
    "expiryDate": "0016-07-14"
  }
}

```
|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|status|string|false|none|This will return Success/Failed|
|code|string|false|none|This will indicate the error code in case of API error|
|message|string|false|none|Error message corresponding to the error code indicating the issue in API call and an indication on how to resolve it.|
|data|PositivePayRule|false|none|none|


### **Delete Rules**
[DELETE /positivepay/rules/{ruleUID}](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/deleteRules/)

**HTTP Method: Delete**

**Description -** Sending a GET request to the **/positivepay/rules/{ruleUID}** endpoint allows users to Delete PositivePay Rule by providing ruleUID in the path of the API request. All the request parameters and objects are specified below- 



|**Name** |**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|ruleUID|path|number(int64)|true|Positive Pay Rule unique id|

**JSON Response**

A successful DELETE request to this endpoint returns the following data

**Response Code - 200**

```yaml Before
{
  "status": "Success or Failure",
  "code": "PP001 etc.",
  "message": "Failed to delete a positive rule: .",
  "ruleUID": 123456789
}

```

|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|status|string|false|none|This will return Success/Failed|
|code|string|false|none|This will indicate the error code in case of API error|
|message|string|false|none|Error message corresponding to the error code indicating the issue in API call and an indication on how to resolve it.|
|ruleUID|number(int64)|false|none|Positive rule unique id|

### **Activate Rules**
[PUT /positivepay/rules/{ruleUID}/activate](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/activateRules/)

**HTTP Method: PUT**

**Description -** Sending a PUT request to the **/positivepay/rules/{ruleUID}/activate** endpoint allows users to activate Positive Pay Rule by providing ruleUID in the path of the API request. All the request parameters and objects are specified below- 



|**Name** |**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|ruleUID|path|string|true|Positive Pay Rule unique id|

**JSON Response**

A successful PUT request to this endpoint returns the following data

**Response Code - 200**

```yaml Before
{
  "status": "Success or Failure",
  "code": "PP001 etc.",
  "message": "Failed to activate or suspend a positive rule: .",
  "ruleUID": 123456789
}

```

|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|status|string|false|none|This will return Success/Failed|
|code|string|false|none|This will indicate the error code in case of API error|
|message|string|false|none|Error message corresponding to the error code indicating the issue in API call and an indication on how to resolve it.|
|ruleUID|number(int64)|false|none|Positive rule unique id|

### **Suspend Rules**
[PUT /positivepay/rules/{ruleUID}/suspend](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/suspendRules/)

**HTTP Method: PUT**

**Description -** Sending a PUT request to PUT **/positivepay/rules/{ruleUID}/suspend** endpoint allows users to suspend Positive Pay Rules by providing ruleUID in the path of the API request. All the request parameters and objects are specified below- 




|**Name** |**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|ruleUID|path|string|true|Positive Pay Rule unique id|

**JSON Response**

A successful PUT request to this endpoint returns the following data

**Response Code - 200**

```yaml Before
{
  "status": "Success or Failure",
  "code": "PP001 etc.",
  "message": "Failed to activate or suspend a positive rule: .",
  "ruleUID": 123456789
}

```
|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|status|string|false|none|This will return Success/Failed|
|code|string|false|none|This will indicate the error code in case of API error|
|message|string|false|none|This will be the detailed error message indicating what failed and how to fix the issue|
|ruleUID|number(int64)|false|none|Positive rule unique id|


### **Search Positive Pay Exceptions**
[POST /positivepay/exception/search](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/searchPositivePayExceptions/)

**HTTP Method: POST**

**Description -** Sending a POST request to **/positivepay/exception/search** endpoint allows users to return positive pay expectations for a given criteria. All the request parameters and objects are specified below- 

**Request Parameters**


|**Name** |**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|body|body|[SearchPositivePayDecisionRequest](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/searchPositivePayExceptions/)|false|none|


**JSON Response**

A successful POST request to this endpoint returns the following data

**Response Code - 200**

```yaml  Before

{
  "status": "Success or Failure",
  "code": "PPD001 etc.",
  "message": "Failed to get the positive pay exception information: .",
  "data": [
    {
      "exceptionUID": "string",
      "paymentUID": "100100",
      "paymentRuleType": "ACH, FEDWIRE, RFP",
      "amount": 123456789,
      "achCompanyID": 122334789,
      "customerAccountNumber": "12387878",
      "beneName": "XYZ Name",
      "exceptionReason": "Amount Mismatch",
      "exceptionDateTime": "2019-08-24",
      "expiryDateTime": "2019-08-24",
      "positivePayDecisionStatus": "string",
      "secCode": "CCD, PPD etc.",
      "approvedBy": "user001",
      "approvedDate": "2019-08-24"
    }
  ]
}

```

|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|status|string|false|none|This will return Success/Failed|
|code|string|false|none|This will indicate the error code in case of API error|
|message|string|false|none|This will be the detailed error message indicating what failed and how to fix the issue|
|ruleUID|[[PositivePayExceptionDecision](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/approveExceptions/)]|false|none|Positive rule unique id|

### **Approve PositivePay Exception**
[PUT /positivepay/exception/{exceptionUID}/approve](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/approveExceptions/)

**HTTP Method: PUT**

**Description -** Sending a PUT request to the **/positivepay/exception/{exceptionUID}/approve** endpoint allows users to approve Positive Pay Exception by passing the ExceptionUID in the API request path. All the request parameters and objects are specified below- 

**Request Parameters**


|**Name** |**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|exceptionUID|path|string|true|A unique identifier associated with the positive pay rule exception|

**JSON Response**

A successful PUT request to this endpoint returns the following data

**Response Code - 200**
```yaml Before

 {
  "status": "Success or Failure",
  "code": "PPD001 etc.",
  "message": "Failed to activate or suspend a positive pay exception: .",
  "exceptionUID": 123456789
}

```

|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|status|string|false|none|This will return Success/Failed|
|code|string|false|none|This will indicate the error code in case of API error|
|message|string|false|none|This will be the detailed error message indicating what failed and how to fix the issue|
|exceptionUID|number(int64)|false|none|Unique identifier associated with positive pay exception|


### **Reject Exceptions**

[PUT /positivepay/exception/{exceptionUID}/reject](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/rejectExceptions/)

**HTTP Method: PUT**

**Description -** Sending a GET request to the **/positivepay/exception/{exceptionUID}/reject** allows users to reject exceptions by passing the exceptionUID in the path of the API request.

All the request parameters and objects are specified below- 

**Request Parameters**


|**Name** |**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|exceptionUID|path|string|true|A unique identifier associated with the positive pay rule exception|

**JSON Response**

A successful GET request to this endpoint returns the following data 

**Response Code - 200**

```yaml Before
{
  "status": "Success or Failure",
  "code": "PPD001 etc.",
  "message": "Failed to activate or suspend a positive pay exception: .",
  "exceptionUID": 123456789
}

```

|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|status|string|false|none|This will return Success/Failed|
|code|string|false|none|This will indicate the error code in case of API error|
|message|string|false|none|This will be the detailed error message indicating what failed and how to fix the issue|
|exceptionUID|number(int64)|false|none|Unique identifier associated with positive pay exception|

### **Approve All Exceptions**
[PUT /positivepay/exception/approveall](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/approveAllExceptions/)

**HTTP Method: PUT**

Description - Sending a PUT request to **/positivepay/exception/approveall** endpoint allows users to approve all positive pay exceptions via payment unique identifier in the API request path. All the request parameters and objects are specified below - 

**Request Parameters**


|**Name** |**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|body|body|[ApproveAllPositivePayExceptionRequest](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/approveAllExceptions/)|false|none|

**JSON Response**

A successful PUT request to this endpoint returns the following data

**Response Code - 200**
```yaml Before
{
  "status": "Success or Failure",
  "code": "PPD001 etc.",
  "message": "Failed to approve all positive pay rule exception: ."
}

```

|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|status|string|false|none|This will return Success/Failed|
|code|string|false|none|This will indicate the error code in case of API error|
|message|string|false|none|This will be the detailed error message indicating what failed and how to fix the issue|