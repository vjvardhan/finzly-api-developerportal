---
title: Create Contact
---
## **Create Contact/Beneficiary**

This API allows the user to add a customer beneficiaries to the customer profile in the CRM system. 

Customer Contact/Beneficiary API help to manage the customer beneficiaries (contacts) in the Finzly CRM system. Once the beneficiaries are defined in the system the contactUID can be used to initiate a payment.

### **Creating Customer Contact**
[POST /customers/{customerUID}/contacts](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/createCustomerContactV2/)

**HTTP Method: POST** 

**Description -** Sending a POST request to "/customers/{customerUID}/contacts" endpoint allows users to create a new contact for an existing customer. Corporate entities acting as a customers can create a contacts, so thus in the future, they don't need to enter the details for payment/transaction purposes. It is a one-time registration for each corporate entity.

**Request Parameters**

|**Name** |**In**|**Type** |**Required** |**Description**|
| :- | :- | :- | :- | :- |
|customerUID|path|integer|true|none|
|body|body|[CustomerContact](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/createCustomerContactV2/)|true|Account Info|

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
|data|[CreateCustomerContactResponse_data](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/createCustomerContactV2/)|false|none|none|