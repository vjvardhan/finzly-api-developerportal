---
title: Contact Management
---
## **Contact Management**

This API allows the creation of customer contacts by setting up their account information.  The user can use the account unique identifier (UID) in the payment request. The customer account can be a type of Checking, Saving or Virtual (Fintech account). Customer Contact APIs help manage the customer beneficiaries (contacts) in the Finzly CRM system. Once the contacts are set up, their UID can be used in the payment APIs as a receiverAccountId.

Using the API, you can:
- Search Customer Contact
- Create Customer Contact
- Get Customer Contacts By ContactUID
- Update Customer Contact


## Customer Contact API

### **Search Customer Contacts**

[GET /customers/{customerUID}/contacts](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/customerapi/operation/searchCustomerContacts/)

**HTTP Method: GET**

**Description -** A GET request containing a series of parameters and objects to the **/customers/{customerUID}/contacts** endpoint is required to search customer contacts. Sending a GET request to the  **/customers/{customerUID}/contacts** endpoint allows Corporate Entities acting as customers to get the list of the details to those customers who are linked with the customerID. All parameters and objects are specified below:


**Request Parameters -** 

Here, the customerUID, Page and Limit are mandatory parameters. CustomerUID will be passed via the PATH of the API request and Page and Limit will be passed via the query section of the API request to fetch the information.



|**Name**|**In**|**Data Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|customerUID|path|integer |true|none|
|contactName|path|string|false|none|
|accountNumber|query|string|false|none|
|page|query|string|true|none|
|limit|query|string|true|none|

**JSON Response**

A successful GET request to this endpoint returns the following data -

**Response Code - 200**

```yaml Before
{
  "status": "Success or Failure",
  "code": "CUST001 etc.",
  "message": "Failed to get a customer contact: ",
  "data": {
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
}


```

**Data Returned Objects**

|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|status|string|false|none|Status of the API request either it will be a success or a failure|
|code|string|false|none|Code associated with the error.|
|message|string|false|none|Error message corresponding to the error code indicating the issue in API call and an indication on how to resolve it.|
|pagination|<p>Pagination</p><p></p>|false|none|none|
|data|[[CustomerContact](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/customerapi/operation/searchCustomerContacts/)]|false|none|none|


### **Creating Customer Contact**
[POST /customers/{customerUID}/contacts](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/customerapi/operation/createCustomerContact/)

**HTTP Method: POST** 

**Description -** Sending a POST request to **/customers/{customerUID}/contacts** endpoint allows users to create a new contact for the existing customer. Corporate entities acting as customers can create a Customer, so thus in the future, they don't need to enter the details for payment/transaction purposes. It is a one-time registration for each corporate entity. All parameters and objects are specified below:

**Request Parameters**

|**Name** |**In**|**Type** |**Required** |**Description**|
| :- | :- | :- | :- | :- |
|customerUID|path|integer|true|none|
|body|body|[CustomerContact](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/customerapi/operation/createCustomerContact/)|true|Account Info|

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
|data|[CreateCustomerContactResponse_data](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/customerapi/operation/createCustomerContact/)|false|none|none|


### **Get Customer Contact Details**
[GET /customers/{customerUID}/contacts/{contactUID}](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/customerapi/operation/getCustomerContactByUID/)

**HTTP Method: GET**

**Description -** A GET request containing contactUID to the **/customers/{customerUID}/contacts/{contactUID}** endpoint is required to retrieve information related to customers. Sending a GET request to this Endpoint allows users to retrieve the customer information from the system using the unique identifier associated with the customer's contact.

**Parameters**

In this Query, we need to pass the two Parameters, CustomerID and ContactID, in the API’s Path to get the response of particular contacts.


|Name |In|Type |Required |Description|
| :- | :- | :- | :- | :- |
|customerUID|path|integer|true|none|
|contactUID|path|[CustomerContact](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/customerapi/operation/getCustomerContactByUID/)|true|none|

```yaml Before
{
  "status": "Success or Failure",
  "code": "CUST001 etc.",
  "message": "Failed to get a customer contact: ",
  "data": {
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
}

```



|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|status|string|false|none|Status of the API request either it will be a success or a failure|
|code|string|false|none|Code associated with the error.|
|message|string|false|none|Error message corresponding to the error code indicating the issue in API call and an indication on how to resolve it.|
|data|CustomerContact|false|none|none|



### **Update Customer Contact Details**
[PUT /customers/{customerUID}/contacts/{contactUID}](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/customerapi/operation/updateCustomerContactByUID/)

**HTTP Method: PUT**

**Description -** Sending a PUT request to **/customers/{customerUID}/contacts/{contactUID}** allows users to update customer contact details. All parameters and objects are specified below:


**Request Parameters**

Here we also need to pass two Parameters, customerUID, and contactUID, in the Path and the further account information for which they want to update the record in the Body section.

|Name|In|Type|Required|Description|
| :- | :- | :- | :- | :- |
|customerUID|path|string|true|none|
|contactUID|path|string|true|none|
|body|body|[CustomerContact](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/customerapi/operation/updateCustomerContactByUID/)|true|Account Information|

**JSON Response**


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
|data|CreateCustomerContactResponse\_data|false|none|none|
