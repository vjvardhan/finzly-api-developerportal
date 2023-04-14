---
title: Get Funding Account
---

## Get Funding Account

You can use this API to get the funding bank account details from the CRM system required to originate a payment.

Execute the below API to get the accountUID (Unique Identifier) associated with the sender’s bank account.

[GET - {{URL}}/customers/{{customer_UID}}/accounts?accountNumber={{account_Number}}](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/customerapi/operation/searchCustomerAccountsV2/)

Where: 
- **customer_UID:** This is the unique ID associated with customer.
- **account_Number:** This is the sender's (funding) bank account number.


**JSON Response**

A successful GET request to this endpoint returns the following data -

**Response Code - 200**

```yaml Before
{
  "status": "Success",
  "code": null,
  "message": null,
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
|data|CustomerBankAccount|false|none|none|


**CustomerBankAccount**


|**Name**|**Type**|**Description**|
| :- | :- | :- |
|accountUID|string|Account unique identifier id assigned by the system|
|name|string|Account Name|
|accountNumber|string|Account Number|
|fboAccountNumber|string|FBO/Virtual Account Number|
|type|string|Account Type such as Deposit, Loan etc.|
|subType|string|Account Sub Type such as Checking, Savings|
|systemOfRecord|string|Which system the bank account holds such as Finzly core, Other Core or External|
|balanceType|string|Account balance type in the core system|
|ledgerBalance|string|Account ledger balance in the core system|
|availableBalance|string|Available balance in the core system|
|availableBalanceStatus|string|Account balance status|
|amountPrecision|string|Amount amountPrecision|
|currency|string|Currency code is ISO format|
|country|string|Country name|
|bankIdType|string|Bank identifier type|
|bankId|string|Bank routing number|
|bankName|string|Name of the bank associated with the bankId|
|enableWires|boolean|Wire status|
|enableOffset|boolean|Whether this bank account is an offset account|
|defaultOffset|boolean|Set this bank account as default offset account|
|feeAccount|boolean|Set the bank account as a fee account|
|returnAccount|boolean|Set the bank account as a return account|
|status|string|Account Status such as Active or InActive|
|externalAccount|AccountExternal|Details of the external account if type is set to External |
