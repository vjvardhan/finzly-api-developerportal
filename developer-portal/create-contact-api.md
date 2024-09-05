---
title: Create Contact
---
## **Create Beneficiary/Contact**

You can use this API to add beneficiaries/contacts to an existing customer profile in the CRM system. Once the beneficiaries are defined in the system you can use the contactUID to initiate a payment. This process will help in reducing the errors during the initiation of the payments. 

### **Creating Customer Contact**
[POST /customers/{customerUID}/contacts](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/customerapi/operation/createCustomerContact/)

**HTTP Method: POST** 

**Description -** Sending a POST request to "/customers/{customerUID}/contacts" endpoint allows users to create new contacts for an existing customer. Corporate entities acting as customers can create contacts. Once created, they don't need to enter the details for payment/transaction purposes. It is a one-time registration for each corporate entity.

**Request Parameters**

|**Name** |**In**|**Type** |**Required** |**Description**|
| :- | :- | :- | :- | :- |
|customerUID|path|integer|true|The unique identifier associated with the customer|
|body|body|CustomerContact|true|Contact Info|

**CustomerContact**

```yaml Before
{
  "externalReferenceId": "string",
  "templateName": "string",
  "name": "string",
  "address": {
    "addressLine1": "111 My Street",
    "addressLine2": "Suite 210",
    "city": "Charlotte",
    "state": "North Carolina",
    "postalCode": "28269",
    "countryCode": "USA",
    "country": "UNITED STATES OF AMERICA"
  },
  "emailAddress": "abc@abc.com",
  "phoneNumber": "123-124-9877",
  "contactBank": {
    "country": "string",
    "accountNo": "string",
    "accountCcy": "string",
    "name": "string",
    "address": {
      "addressLine1": "111 My Street",
      "addressLine2": "Suite 210",
      "city": "Charlotte",
      "state": "North Carolina",
      "postalCode": "28269",
      "countryCode": "USA",
      "country": "UNITED STATES OF AMERICA"
    },
    "nationalCode": "0125487",
    "swiftCode": "USBNX000"
  },
  "intermediaryBank": {
    "country": "string",
    "name": "string",
    "nationalCode": "string",
    "swiftCode": "string",
    "coverMessageRequired": "string",
    "address": {
      "addressLine1": "111 My Street",
      "addressLine2": "Suite 210",
      "city": "Charlotte",
      "state": "North Carolina",
      "postalCode": "28269",
      "countryCode": "USA",
      "country": "UNITED STATES OF AMERICA"
    }
  },
  "otherInfo": {
    "beneficiaryNotes": "string",
    "otherBeneBankInfo": "string"
  },
  "regulartoryReporting": [
    {
      "key": "string",
      "value": "string"
    }
  ]
}
```


**JSON Response**

A successful POST request to this endpoint returns the following data -

```yaml Before
{
  "status": "Success or Failure",
  "code": "CUST001 etc.",
  "message": "Failed to create a customer contact: ",
  "data": {
    "customerContactUID": "string",
    "externalReferenceId": "string"
  }
}

```

|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|status|string|false|none|Status of the API request either it will be a success or a failure|
|code|string|false|none|Code associated with the error.|
|message|string|false|none|Error message corresponding to the error code indicating the issue in API call and an indication on how to resolve it.|
|data|CreateCustomerContactResponse_data|false|none|Response Data|


**CreateCustomerContactResponse_data**

|**Name**|**Type**|**Description**|
| :- | :- | :- |
|customerContactUID|string|Unique identifier assigned by the system|
|externalReferenceId|string|External referenceID provided to the API|
