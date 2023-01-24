---
title: Finzly Customer Account API
---

## Account Management

Customer Accounts APIs help users get all the accounts associated with their customer in a single call. You can enhance the customer experience by providing them with the most updated balance. Besides, you can further add value by tracking payment transactions related to these individual accounts.

The following **supported API functions** helps you to understand the current customer accounts capabilities exposed via APIs:

1. Search Customer Account
2. Create Customer Account
3. Get Customer Account
4. Update Customer Account
5. Delete Customer Account

## **Supported Customer Accounts API functions**
### **Search Customer Account**
[HTTP Method: GET](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/searchCustomerAccountsV2/)

**Description** - Sending a GET request to the Search Customers Account Endpoint will allow users to search for customer accounts using parameters customerUID, accountType, and others. This can be used to search the details of customers' accounts registered with the corporate entity. The details will be provided in bulk and not specific. All the request parameters and objects are specified below:

**Request Parameters**

Customer UID must be passed in the path of the API request to search for customers. Rest of the parameters are optional


|Name|In|Data Type|Required|Description|
| :- | :- | :- | :- | :- |
|customerUID|path|string|true||
|accountType|query|string|false|Type of Customer Account|
|status|query|string|false|<p></p><p></p>|
|currency|query|string|false|Customer ID|
|wireEnabled|query|string|false|none|
|accountNumber|query|string|false|Federal Tax ID|


**JSON Response**

A successful GET request to this endpoint returns the following data -

``` yaml Before

{
  "status": "Success or Failure",
  "code": "ACC001 etc.",
  "message": "Failed to get an account: ",
  "data": [
    {
      "accountUID": "100100",
      "name": "Checking",
      "accountNumber": "1122345",
      "fboAccountNumber": "2233445",
      "type": "DEPOSIT or LOAN",
      "subType": "Checking, Saving, Psuedo",
      "systemOfRecord": "Other Core or External",
      "balanceType": "DDA etc.",
      "ledgerBalance": "24000.00",
      "availableBalance": "25000.00",
      "availableBalanceStatus": "NSF",
      "amountPrecision": "string",
      "currency": "USD",
      "country": "UNITED STATE OF AMERICA etc.",
      "bankId": "11223498",
      "bankName": "Chase etc.",
      "bankIdType": "By ABA or By Address",
      "enableWires": false,
      "enableOffset": false,
      "defaultOffset": false,
      "feeAccount": false,
      "returnAccount": false,
      "status": "Active etc.",
      "externalAccount": {
        "externalProvider": "Plaid",
        "externalId": "1234567",
        "externalAuthToken": "1234567"
      }
    }
  ]
}
```


|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|status|string|false|none|Status of the API request either it will be a success or a failure|
|code|string|false|none|Code associated with the error.|
|message|string|false|none|Error message corresponding to the error code indicating the issue in API call and an indication on how to resolve it.|
|data|[[CustomerBankAccount](https://apidocs.finzly.net/dashboard?java=#schemacustomerbankaccount)]|false|none|none|

**Customer Bank Account**


|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|accountUID|string|false|none|Account unique identifier assigned by the system|
|name|string|false|none|Account Name|
|accountNumber|string|false|none|Account Number|
|fboAccountNumber|string|false|none|FBO Account Number|
|type|string|false|none|Account Type|
|subType|string|false|none|Account Type|
|systemOfRecord|string|false|none|Identifier of the system of record|
|balanceType|string|false|none|Account balance type in the bank core system|
|ledgerBalance|string|false|none|Account ledger balance amount in the bank core system|
|availableBalance|string|false|none|Account balance amount in the bank core system|
|availableBalanceStatus|string|false|none|Account balance status in the bank core system|
|amountPrecision|string|false|none|Amount amountPrecision|
|currency|string|false|none|Currency code is ISO format|
|country|string|false|none|Country name|
|bankId|string|false|none|Bank routing number|
|bankName|string|false|none|Name of the bank associated with the bankId|
|bankIdType|string|false|none|Bank identifier type|
|enableWires|boolean|false|none|Wire status|
|enableOffset|boolean|false|none|Whether the accountNumber is a Offset account|
|defaultOffset|boolean|false|none|Default offset account|
|feeAccount|boolean|false|none|Whether the accountNumber is a Fee account|
|returnAccount|boolean|false|none|Whether the accountNumber is a Return account|
|status|string|false|none|Account Status|
|externalAccount|[AccountExternal](https://apidocs.finzly.net/dashboard?java=#schemaaccountexternal)|false|none|none|


### **Create Customer Account**
[POST /v2/customers/{customerUID}/accounts](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/createCustomerAccountV2/)

**HTTP Method: POST**	

**Description -** Sending a POST request to /v2/customers/{customerUID}/accounts endpoint allows users to create a customer account using parameters including customerUID. All parameters and objects are specified below:

**Request Parameters**

The customer uid must be passed in the path of API request. In the body section must pass the details of the user account to be createds.

|Name |In|Type |Required |Description|
| :- | :- | :- | :- | :- |
|customerUID|path|integer|true|none|
|body|body|[CreateAccountRequest](https://apidocs.finzly.net/dashboard#schemacreateaccountrequest)|true|Account Info|


**JSON Response**

A successful POST request to this endpoint returns the following data -

**Response Code - 200**

``` yaml Before
{
  "status": "Success or Failure",
  "code": "ACC001 etc.",
  "message": "Failed to create an account: ",
  "data": {
    "accountUID": "string",
    "externalReferenceId": "string"
  }
}

```

|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|status|string|false|none|Status of the API request either it will be a success or a failure|
|code|string|false|none|Code associated with the error.|
|message|string|false|none|Error message corresponding to the error code indicating the issue in API call and an indication on how to resolve it.|
|data|[CreateAccountResponse_data](https://apidocs.finzly.net/dashboard?java=#schemacreateaccountresponse_data)|false|none|none|

**Create Account Response Data**


``` yaml Before
{
  "accountUID": "string",
  "externalReferenceId": "string"
}

```
|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|accountUUID |string|false|none|none|
|externalReferenceId|string|false|none|none|


### **Get Customers**
[GET /v2/customers/{customerUID}/accounts/{accountUID}](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/getCustomerAccountByAccountUIDV2/)

**HTTP  Method: GET**	

**Description -** Sending a GET request to /v2/customers/{customerUID}/accounts/{accountUID} endpoint allows users to retrieve a customer account associated with parameters including customerUID and accountUID. All parameters and objects are specified below -

**Request Parameters**

Two parameters need to be passed in the path of the API request, customerUID and account UID of the user registered with customer/corporate.


|**Name**|**In**|**Data Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|customerUID|path|string|true|none|
|accountUID|path|string|true|none|
|includeAccountBalance|query|string|false|<p></p><p>none</p>|
|page|query|string|false|none|
|limit|query|string|false|none|


**JSON Response**

A successful GET request to this endpoint returns the following data -

**Response Code - 200**

```yaml Before
{
  "status": "Success or Failure",
  "code": "ACC001 etc.",
  "message": "Failed to get an account: ",
  "data": {
    "accountUID": "100100",
    "name": "Checking",
    "accountNumber": "1122345",
    "fboAccountNumber": "2233445",
    "type": "DEPOSIT or LOAN",
    "subType": "Checking, Saving, Psuedo",
    "systemOfRecord": "Other Core or External",
    "balanceType": "DDA etc.",
    "ledgerBalance": "24000.00",
    "availableBalance": "25000.00",
    "availableBalanceStatus": "NSF",
    "amountPrecision": "string",
    "currency": "USD",
    "country": "UNITED STATE OF AMERICA etc.",
    "bankId": "11223498",
    "bankName": "Chase etc.",
    "bankIdType": "By ABA or By Address",
    "enableWires": false,
    "enableOffset": false,
    "defaultOffset": false,
    "feeAccount": false,
    "returnAccount": false,
    "status": "Active etc.",
    "externalAccount": {
      "externalProvider": "Plaid",
      "externalId": "1234567",
      "externalAuthToken": "1234567"
    }
  }
}

```
|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|status|string|false|none|Status of the API request either it will be a success or a failure|
|code|string|false|none|Code associated with the error.|
|message|string|false|none|Error message corresponding to the error code indicating the issue in API call and an indication on how to resolve it.|
|data|[CustomerBankAccount](https://apidocs.finzly.net/dashboard?java=#schemacustomerbankaccount)|false|none|none|


### **Update Customer Account**
[PUT /v2/customers/{customerUID}/accounts/{accountUID}](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/updateCustomerAccountByAccountUIDV2/)

**HTTP  Method: PUT**

**Description -** Sending a PUT request to v2/customers/{customerUID}/accounts/{accountUID} endpoint with parameters including customerUID and accountUID allows users to update customer accounts. All parameters and objects are specified below:

**Request Parameters**

Two parameters need to be passed in the path of the API request, customerUID and account UID of the user registered with customer/corporate. Body section will include the details of the user account which we want to update.

|**Name**|**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|customerUID|path|string|true|none|
|accountUID|path|string|true|none|
|body|body|[UpdateAccountRequest](https://apidocs.finzly.net/dashboard#schemaupdateaccountrequest)|true|Account Info|

**JSON Response**

A successful request to this endpoint returns the following data - 

Response Code - 200	

```yaml Before
{
  "status": "Success or Failure",
  "code": "ACC001 etc.",
  "message": "Failed to update an account: ",
  "data": {
    "accountUID": "string",
    "externalReferenceId": "string"
  }
}

```
|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|status|string|false|none|Status of the API request either it will be a success or a failure|
|code|string|false|none|Code associated with the error.|
|message|string|false|none|Error message corresponding to the error code indicating the issue in API call and an indication on how to resolve it.|
|data|[UpdateAccountResponse_data](https://apidocs.finzly.net/dashboard?java=#schemaupdateaccountresponse_data)|false|none|none|

**Update Account Response data**

```yaml Before
{
  "accountUID": "string",
  "externalReferenceId": "string"
}

```

|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|accountUUID |string|false|none|Account unique identifier assigned by the system|
|externalReferenceId|string|false|none|none|


### **Delete Customer Account**

[DELETE /v2/customers/{customerUID}/accounts/{accountUID}](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/deleteCustomerAccountByAccountUIDV2/)

**HTTP  Method: DELETE**

**Description - Sending a DELETE request to the** /v2/customers/{customerUID}/accounts/{accountUID} endpoint with parameters including CustomerUID and AccountUID allows users to delete a customer account. All parameters and objects are specified below:

**Request Parameters**

Two parameters need to be passed in the path of the API request, customerUID and account UID of the user registered with customer/corporate to delete the account.


|**Name**|**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|customerUID|path|string|true|none|
|accountUID|path|string|true|none|


**JSON Response**

A successful DELETE request to this endpoint will return the following data -

**Response Code - 200**

```yaml Before
{
  "status": "Success or Failure",
  "code": "ACC001 etc.",
  "message": "Failed to update an account: ",
  "data": {
    "accountUID": "string",
    "externalReferenceId": "string"
  }
}

```
|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|status|string|false|none|Status of the API request either it will be a success or a failure|
|code|string|false|none|Code associated with the error.|
|message|string|false|none|Error message corresponding to the error code indicating the issue in API call and an indication on how to resolve it.|
|data|[UpdateAccountResponse_data](https://apidocs.finzly.net/dashboard?java=#schemaupdateaccountresponse_data)|false|none|none|


**Update Account Response data**

```yaml Before
{
  "accountUID": "string",
  "externalReferenceId": "string"
}

```

|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|accountUUID |string|false|none|Account unique identifier assigned by the system|
|externalReferenceId|string|false|none|none|