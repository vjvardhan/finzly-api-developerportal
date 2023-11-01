---
title: Customer Management
---

## Customer Management

Customer APIs entitle the setup of clients as part of customer onboarding to enable them to perform financial transactions on their behalf. These APIs will also enable users to search & maintain these onboarded clients, update any modifications in client information and create/update their beneficiaries (contacts). The APIs support the following:

- Create Customer
- Search Customer
- Get Customer By CustomerUID
- Update Customer

__Add Client (of Fintech)__

__HTTP Method: POST__

__Description__ - Using this API, the user can add a CRM entity to FinzlyOS. This API allows them to create customer types such as Customer, Corporate, Downstream partner (FinTech), Third Party Customer (Customer of a FinTech), and Financial Institutions.


## **Customer API**
### **Search Customer**

[GET /customers](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/customerapi/operation/searchCustomers/)

__HTTP Method: GET__

__Description__ - A GET request containing a series of parameters and objects to the **GET /customers** endpoint is required to search for customers. Sending a GET request to the Search Customers Endpoint will allow users to search for customers using parameters such as legal name, short name, etc. All parameters and objects are specified below:


__Request Parameters__

Using Page and Limits which are the mandatory parameters, we can set the number of search result records we want to get through the API request. Other optional parameters can be passed according to the user requirements as follows:

|Name | In | Data Type | Required | Description |
|---|---|---|---|---|
| legalName | Query | String | false | Customer's legal name | 
| CustomerType | Query | String | false | Type of Customer |
| shortName | Query | String | false | Customer's short name |
| CustomerID | Query | String | false | ACH company ID is a 10-digit identifier used by banks and Nacha, the operator of the ACH network, to identify the entity collecting payments or sending money via ACH (also referred to as an “originator”) |
| Page | Query | String | True | none |
| limit | Query | String | True | none |

__JSON Response__ for GET request to __/customers__ endpoint

A successful GET request to __/customers__ endpoint will return the following data - 

__Response Code - 200__

```yaml Before
{
  "externalReferenceId": "tran12780",
  "legalName": "DEMO Bank",
  "shortName": "DMOB",
  "customerUID": 111222,
  "customerType": "Consumer or Corporate or Downstream Partner or Processing Org or Financial Institution",
  "taxId": "123456789",
  "achCompanyID": "1234567899",
  "customerId": "12347890",
  "status": "Active, Suspended,New,Pending",
  "lei": "ABC1234",
  "swiftcode": "BOFAUS3N",
  "language": "English",
  "emailAddress": "abc@bank.com",
  "phoneNumber": "1112223333",
  "faxNumber": "1231249877",
  "website": "http://www.bank.com",
  "logoUrl": "https://www.google.com/images/branding/googlelogo/2x/googlelogo_color_92x30dp.png",
  "linkedinUrl": "https://www.linkedin.com/company/finzly",
  "twitterUrl": "https://twitter.com/bank",
  "legalAddress": {
    "addressLine1": "111 My Street",
    "addressLine2": "Suite 210",
    "city": "Charlotte",
    "state": "North Carolina",
    "postalCode": "28269",
    "countryCode": "USA",
    "country": "UNITED STATES OF AMERICA"
  },
  "mailAddressSameAsLegal": true,
  "mailingAddress": {
    "addressLine1": "111 My Street",
    "addressLine2": "Suite 210",
    "city": "Charlotte",
    "state": "North Carolina",
    "postalCode": "28269",
    "countryCode": "USA",
    "country": "UNITED STATES OF AMERICA"
  },
  "relationshipType": "Customer or Bank or ThirdParty or Self",
  "partnerOrgShortName": "TESTBANK",
  "processingOrgShortName": "POBANK",
  "costCenter": "123123121",
  "relationshipManager": "testuser",
  "originatingOfficer": "testuser",
  "parentEntityShortName": "TESTBANK",
  "addtionalProfileDetails": [
    {
      "creditclient": true,
      "accountanalysis": true,
      "sso": true,
      "billingcustomer": true,
      "restrictedaccess": true,
      "achPositivePay": true,
      "achWhitelist": true,
      "achNonPrefund": true,
      "achNonPrefundLimit": "string",
      "paymentFileAuthentication": true,
      "detailsofCharge": "OUR",
      "fxPricingTier": "string",
      "crediValueAdjustment": "string"
    }
  ],
  "secCodes": [
    "WEB"
  ],
  "note": "Notes for the customer",
  "legalEntityAccessSettings": {
    "allowOnlineAccess": true,
    "userPinForNewEntry": true,
    "userDualApproval": true,
    "userPinForApproval": true,
    "notificationsDualApproval": true,
    "customerPinForNewEntry": true,
    "customerDualApproval": true,
    "customerPinForApproval": true,
    "benePinForNewEntry": true,
    "beneDualApproval": true,
    "benePinForApproval": true,
    "paymentPinForNewEntry": true,
    "paymentLimitforFirstApprover": 0,
    "paymentDualApproval": true,
    "paymentLimitforSecondApprover": 0,
    "paymentNumberOfApprovers": 0,
    "paymentPinForApproval": true,
    "feeTierForApproval": true
  }
}
```

__API Response Objects-__

|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|status|string|false|none|Status of the API request either it will be a success or a failure|
|code|string|false|none|Code associated with the error.|
|message|string|false|none|Error message corresponding to the error code indicating the issue in API call and an indication on how to resolve it.|
|pagination|[Pagination](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/customerapi/operation/searchCustomers/)|false|none|none|
|data|[[GetCustomerDetailResponse](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/customerapi/operation/searchCustomers/)]|false|none|none|


**Get Customer Detail Response**

```yaml Before
    {
  "externalReferenceId": "tran12780",
  "legalName": "DEMO Bank",
  "shortName": "DMOB",
  "customerUID": 111222,
  "customerType": "Consumer or Corporate or Downstream Partner or Processing Org or Financial Institution",
  "taxId": "123456789",
  "achCompanyID": "1234567899",
  "customerId": "12347890",
  "status": "Active, Suspended,New,Pending",
  "lei": "ABC1234",
  "swiftcode": "BOFAUS3N",
  "language": "English",
  "emailAddress": "abc@bank.com",
  "phoneNumber": "1112223333",
  "faxNumber": "1231249877",
  "website": "http://www.bank.com",
  "logoUrl": "https://www.google.com/images/branding/googlelogo/2x/googlelogo_color_92x30dp.png",
  "linkedinUrl": "https://www.linkedin.com/company/finzly",
  "twitterUrl": "https://twitter.com/bank",
  "legalAddress": {
    "addressLine1": "111 My Street",
    "addressLine2": "Suite 210",
    "city": "Charlotte",
    "state": "North Carolina",
    "postalCode": "28269",
    "countryCode": "USA",
    "country": "UNITED STATES OF AMERICA"
  },
  "mailAddressSameAsLegal": true,
  "mailingAddress": {
    "addressLine1": "111 My Street",
    "addressLine2": "Suite 210",
    "city": "Charlotte",
    "state": "North Carolina",
    "postalCode": "28269",
    "countryCode": "USA",
    "country": "UNITED STATES OF AMERICA"
  },
  "relationshipType": "Customer or Bank or ThirdParty or Self",
  "partnerOrgShortName": "TESTBANK",
  "processingOrgShortName": "POBANK",
  "costCenter": "123123121",
  "relationshipManager": "testuser",
  "originatingOfficer": "testuser",
  "parentEntityShortName": "TESTBANK",
  "addtionalProfileDetails": [
    {
      "creditclient": true,
      "accountanalysis": true,
      "sso": true,
      "billingcustomer": true,
      "restrictedaccess": true,
      "achPositivePay": true,
      "achWhitelist": true,
      "achNonPrefund": true,
      "achNonPrefundLimit": "string",
      "paymentFileAuthentication": true,
      "detailsofCharge": "OUR",
      "fxPricingTier": "string",
      "crediValueAdjustment": "string"
    }
  ],
  "secCodes": [
    "WEB"
  ],
  "note": "Notes for the customer",
  "legalEntityAccessSettings": {
    "allowOnlineAccess": true,
    "userPinForNewEntry": true,
    "userDualApproval": true,
    "userPinForApproval": true,
    "notificationsDualApproval": true,
    "customerPinForNewEntry": true,
    "customerDualApproval": true,
    "customerPinForApproval": true,
    "benePinForNewEntry": true,
    "beneDualApproval": true,
    "benePinForApproval": true,
    "paymentPinForNewEntry": true,
    "paymentLimitforFirstApprover": 0,
    "paymentDualApproval": true,
    "paymentLimitforSecondApprover": 0,
    "paymentNumberOfApprovers": 0,
    "paymentPinForApproval": true,
    "feeTierForApproval": true
  }
}

```

**Data Returned Objects**

|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|externalReferenceId|string|false|none|Unique reference id from a system outside of finzly. The external reference id can be used by the finzly for the request tracing purpose (if needed).|
|legalName|string|false|none|Customer's legal name|
|shortName|string|false|none|Customer's short name|
|customerUID|string|false|none|The unique identifier associated with the customer record assigned by the Finzly system.|
|customerType|string|false|none|Type of the customers in the Finzly CRM system|
|taxId|string|false|none|A tax id that the US government uses to identify business entities located in the US number|
|achCompanyID|string|false|none|<p>ACH company ID is a 10-digit identifier used by banks and Nacha, the operator of the ACH network, to identify the entity collecting payments or sending money via ACH (also referred to as an “originator”)</p><p></p>|
|customerId|string|false|none|Customer id assigned by the user.|
|status|string|false|none|Current status of the customer.|
|lei|string|false|none|Legal Entity Identifier (LEI) associated with the customer|
|swiftcode|string|false|none|SWIFT code that identifies your bank, country, location, and branch|
|language|string|false|none|language|
|emailAddress|string|false|none|Customer email address|
|phoneNumber|string|false|none|Customer phone number|
|faxNumber|string|false|none|Customer fax number|
|website|string|false|none|Customer fax number|
|logoUrl|string|false|none|Customer logo url|
|linkedinUrl|string|false|none|Company linkedin URL|
|<p>twitterUrl</p><p></p><p></p>|string|false|none|Customer twitter url|
|legalAddress|[CustomerAddress](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/customerapi/operation/searchCustomers/)|false|none|none|
|mailAddressSameAsLegal|boolean|false|none|none|
|mailingAddress|[CustomerAddress](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/customerapi/operation/searchCustomers/)|false|none|none|
|relationshipType|string|false|none|Relationship Type|
|partnerOrgShortName|string|false|none|This is the shortname associated with the customer defined in the CRM system as 'Downstream Partner'. This is required only if the customer relationshipType is Third party|
|processingOrgShortName|string|false|none|This is the shortname associated with the processing org the customer is associated with.|
|costCenter|string|false|none|Cost Center associated with the customer entity|
|relationshipManager|string|false|none|Relationship manager name. It needs to be a valid user login id in the finzly system.|
|originatingOfficer|string|false|none|Originating Officer name. It needs to be a valid user login id in the finzly system.|
|parentEntityShortName|string|false|none|This is the short name associated with the existing customer legal entity act as a parent entity|
|addtionalProfileDetails|[[CustomerAdditonalProfileDetails](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/customerapi/operation/searchCustomers/)]|false|none|none|
|secCodes|string|false|none|Provide all valid SEC-Standard Entry Class codes allowed for the given customer entity|
|note|string|false|none|Free form text to leave any notes for the customer entity.|
|legalEntityAccessSettings|[LegalEntityAccessSettings](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/customerapi/operation/searchCustomers/)|false|none|none|


*Note the following about the results:*

- *Request URL: ​Shows what executed.*
- *Response Headers:​ Contains messages about the success or failure of the request.* 
- *Response Body: ​Contains a JSON array of the results.* 
- *Curl Command Line: ​Contains a form of the request that you can copy and paste to execute at the command line or in scripts.*

### **Creating Customer**
[POST /customers](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/customerapi/operation/createCustomer/)

**HTTP Method:** **POST**

**Description -** Sending a POST request to Customers Endpoint will allow the users to create a customer as a Corporate Account for getting the features and using further options. Finzly is providing a dashboard where corporate customers can create their account and use the settings later on as per their convenience. In order to create a customer a POST request containing a series of parameters and objects to the **POST /customers** endpoint is required. All parameters and objects are specified below -

**Request Parameters**

The entire data will be passed through the body section. 

|Name |In|Type|Required|Description|
| :- | :- | :- | :- | :- |
|body|body|` `[CreateCustomerRequest](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/customerapi/operation/createCustomer/)|true|Customer Details|


**JSON Response** for POST request to **/customers** endpoint will return the following data - 

**Response Code - 200**

``` yaml Before
200 Response
{
  "status": "Success or Failure",
  "code": "CUST001 etc.",
  "message": "Failed to create a customer due to the mandatory attribute  is not provide.",
  "data": {
    "customerUID": "123",
    "externalReferenceId": "string",
    "shortName": "string",
    "customerEntityStatus": "New"
  }
}


```

**Data Returned Objects**

|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|status|string|false|none|This will return Success/Failed|
|code|string|false|none|This will indicate the error code in case of API error|
|message|string|false|none|This will be the detailed error message indicating what failed and how to fix the issue|
|data|<p>[CreateUpdateCustomerResponse_data](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/customerapi/operation/createCustomer/)</p><p></p>|false|none|none|


**Note the following about the results:**

- **Request URL:**  ​Shows what executed.
- **Response Headers:​**  Contains messages about the success or failure of the request.
- **Response Body:** ​ Contains a JSON array of the results.
- **Curl Command Line:** ​ Contains a form of the request that you can copy and paste to execute at the command line or in scripts.

### **Getting Customer Information by customerUID**

[GET /customers/{customerUID}](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/customerapi/operation/getCustomerByCustomerUID/)

**HTTP Method: GET**

**Description** - A GET request containing customerUID to the **/customers/{customerUID}** endpoint is required to retrieve information related to customers. Sending a GET request to this Endpoint allows users to retrieve the customer information from the system using the unique identifier associated with the customer. By passing the Customer ID in the path of the API request, we can get the full details in the response.

**Request Parameters**

Here we need to pass the CustomerID as a Path in the API request to get the response.


|Name |In|Data Type|Required|Description|
| :- | :- | :- | :- | :- |
|customerUID|path|` `string|true|none|


**Success Response**

A successful GET request to **/customers/{customerUID}** endpoint returns the following data 

**Response Code - 200**

```yaml Before 
200 Response
[
  {
    "status": "Success or Failure",
    "code": "CUST001 etc.",
    "message": "Failed to get the customer: ",
    "pagination": {
      "totalRecords": 100,
      "returnedRecords": 10,
      "pageReturned": 2,
      "pageSize": 10
    },
    "data": [
      {
        "externalReferenceId": "tran12780",
        "legalName": "DEMO Bank",
        "shortName": "DMOB",
        "customerUID": 111222,
        "customerType": "Consumer or Corporate or Downstream Partner or Processing Org or Financial Institution",
        "taxId": "123456789",
        "achCompanyID": "1234567899",
        "customerId": "12347890",
        "status": "Active, Suspended,New,Pending",
        "lei": "ABC1234",
        "swiftcode": "BOFAUS3N",
        "language": "English",
        "emailAddress": "abc@bank.com",
        "phoneNumber": "1112223333",
        "faxNumber": "1231249877",
        "website": "http://www.bank.com",
        "logoUrl": "https://www.google.com/images/branding/googlelogo/2x/googlelogo_color_92x30dp.png",
        "linkedinUrl": "https://www.linkedin.com/company/finzly",
        "twitterUrl": "https://twitter.com/bank",
        "legalAddress": {
          "addressLine1": "111 My Street",
          "addressLine2": "Suite 210",
          "city": "Charlotte",
          "state": "North Carolina",
          "postalCode": "28269",
          "countryCode": "USA",
          "country": "UNITED STATES OF AMERICA"
        },
        "mailAddressSameAsLegal": true,
        "mailingAddress": {
          "addressLine1": "111 My Street",
          "addressLine2": "Suite 210",
          "city": "Charlotte",
          "state": "North Carolina",
          "postalCode": "28269",
          "countryCode": "USA",
          "country": "UNITED STATES OF AMERICA"
        },
        "relationshipType": "Customer or Bank or ThirdParty or Self",
        "partnerOrgShortName": "TESTBANK",
        "processingOrgShortName": "POBANK",
        "costCenter": "123123121",
        "relationshipManager": "testuser",
        "originatingOfficer": "testuser",
        "parentEntityShortName": "TESTBANK",
        "addtionalProfileDetails": [
          {
            "creditclient": true,
            "accountanalysis": true,
            "sso": true,
            "billingcustomer": true,
            "restrictedaccess": true,
            "achPositivePay": true,
            "achWhitelist": true,
            "achNonPrefund": true,
            "achNonPrefundLimit": "string",
            "paymentFileAuthentication": true,
            "detailsofCharge": "OUR",
            "fxPricingTier": "string",
            "crediValueAdjustment": "string"
          }
        ],
        "secCodes": [
          "WEB"
        ],
        "note": "Notes for the customer",
        "legalEntityAccessSettings": {
          "allowOnlineAccess": true,
          "userPinForNewEntry": true,
          "userDualApproval": true,
          "userPinForApproval": true,
          "notificationsDualApproval": true,
          "customerPinForNewEntry": true,
          "customerDualApproval": true,
          "customerPinForApproval": true,
          "benePinForNewEntry": true,
          "beneDualApproval": true,
          "benePinForApproval": true,
          "paymentPinForNewEntry": true,
          "paymentLimitforFirstApprover": 0,
          "paymentDualApproval": true,
          "paymentLimitforSecondApprover": 0,
          "paymentNumberOfApprovers": 0,
          "paymentPinForApproval": true,
          "feeTierForApproval": true
        }
      }
    ]
  }

```


### **Updating Customers**

[PUT /customers/{customerUID}](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/customerapi/operation/updateCustomerByCustomerUID/)

**HTTP Method: PUT**

**Description -** A PUT request containing a series of parameters and objects to the **/customers/{customerUID}** endpoint is required to update customers. Sending a PUT request to the **/customers/{customerUID}** endpoint allows users to update information related to any existing customer type using parameters. All parameters and objects are specified below:

**Request Parameters**

Here we need to Pass the Customer ID in the path of the API request and Data via the body section to update the record on behalf of the customerID and data will be passed via the body section to update the record on the behalf of customerID.

|Name|In|Type|Required|Description|
| :- | :- | :- | :- | :- |
|customerUID|path|string|true|none|
|body|body|[UpdateCustomerRequest](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/customerapi/operation/updateCustomerByCustomerUID/)|true|Customer details|

**JSON Response**

**Response Code - 200**

```yaml Before 
{
  "status": "Success or Failure",
  "code": "CUST001 etc.",
  "message": "Failed to create a customer due to the mandatory attribute  is not provide.",
  "data": {
    "customerUID": "123",
    "externalReferenceId": "string",
    "shortName": "string",
    "customerEntityStatus": "New"
  }
}


```


```yaml Before 
{
  "customerUID": "123",
  "externalReferenceId": "string",
  "shortName": "string",
  "customerEntityStatus": "New"
}


```

**Data Returned Objects**

|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|status|string|false|none|This will return Success/Failed|
|code|string|false|none|This will indicate the error code in case of API error|
|message|string|false|none|This will be the detailed error message indicating what failed and how to fix the issue|
|data|<p>[CreateUpdateCustomerResponse_data](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/customerapi/operation/updateCustomerByCustomerUID/)</p><p></p>|false|none|none|




|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|customerUID|string|false|none|Customer id within Finzly's CRM system|
|externalReferenceId|string|false|none|none|
|shortName|string|false|none|none|
|customerEntityStatus|string|false|none|Status of the customer|




