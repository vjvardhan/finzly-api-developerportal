---
title: Initiate a payout  
---

## How to initiate a payout

You can initiate a payment using the following simple steps. Finzly Connect single payment API supports the payment origination for the various payment rails such as ACH, Fedwire, SWIFT, and RTP/FedNow based upon the speed preference.


### **Execute a payout request** 

Prepare the payout request by providing the simple payment instructions such as sender ID, receiver ID, payment amount, notes and speed.

[POST /payments/creditrequest](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/paymentapi/operation/createCreditPayment/)

**HTTP Method: POST**


```yaml Before

{
	"externalReferenceId": "PaymentRef100",
	"paymentAmount": 125.13,
	"paymentCurrency": "USD",
	"speed": "Economy",
	"paymentNotes": "Notes",
	"sender": {
		"accountUID": "58"
	},
	"receiver": {
		"accountUID": "29"
	}
}

```

**Payment Speed Details**

The user can define the speed of money movement as part of their preference to execute the payment. The cost of the payment depends on the sponsor bank, while the speed is setup using different parameters that correspond to different payment rails that determine how quickly money can be moved.


|**Speed**|**Speed Description**|
| :- | :- |
|Economy|Regular ACH|
|Economy Plus|Same Day ACH|
|Express|Fedwire|
|Instant|RTP or FedNow based upon the configuration|
|SPOT|Spot international payment|
|ON|Same day international payment|
|TN|Next day international payment|



### **>> Identify the sender bank (funding) account unique identifier (accountUID)**

Execute the below API to get the accountUID (Unique Identifier) associated with the sender’s bank account.

[GET - {{URL}}/customers/{{customer_UID}}/accounts?accountNumber={{account_Number}}](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/customerapi/operation/searchCustomerAccounts/)

Where: 
- **customer_UID:** This is the unique ID associated with customer.
- **account_Number:** This is the sender's (funding) bank account number.


**JSON Response**

```yaml Before
{
    "status": "Success",
    "data": {
        "accountUID": 58,
        "name": "Test DDA Account 1",
        "accountNumber": "****0001",
        "fboAccountNumber": "",
        "type": "DEPOSIT",
        "subType": "CHECKING",
        "systemOfRecords": "Other Core",
        "balanceType": "Available", ...
    }
} 

```

**Note: Get the sender bank (funding) account ID from the "accountUID" attribute.**


### **>> Identify the sender unique identifier value (accountUID)**

Execute the below API to get the accountUID (Unique Identifier) associated with the sender bank account number.

[GET - {{URL}}/customers/{{customer_UID}}/accounts?accountNumber={{account_Number}}](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/customerapi/operation/searchCustomerAccounts/)

Where: 
- **customer_UID:** This is the unique ID associated with customer.
- **account_Number:** This is the sender (funding) bank account number.


**JSON Response**

```yaml Before
{
    "status": "Success",
    "data": {
        "accountUID": 58,
        "name": "Test DDA Account 1",
        "accountNumber": "****0001",
        "fboAccountNumber": "",
        "type": "DEPOSIT",
        "subType": "CHECKING",
        "systemOfRecords": "Other Core",
        "balanceType": "Available", ...
    }
} 

```


**Note: Use the "accountUID" attribute value for the sender accountUID.**


### **>> Identify the receiver unique identifier value (accountUID)**

Execute the below API to get the contactUID (Unique Identifier) associated with the contact/beneficiary/receiver bank account.

[GET - {{URL}}/customers/{{customer_UID}}/contacts?accountNumber={{account_Number}}&page=1&records=1](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/customerapi/operation/searchCustomerContacts/)

Where: 
- **customer_UID:** This is the unique ID associated with the customer.
- **account_Number:** This is the account number.
- **page:** Number of page needed from the search query.
- **records:** Number of records needed on a page.

**Receiver Account Response:**  

```yaml Before
{
    "status": "Success",
    "code": null,
    "message": null,
    "pagination": {
        "totalRecords": 1,
        "returnedRecords": 1,
        "pageReturned": 0,
        "pageSize": 1
    },
    "data": [
        {
            "contactUID": "29",
            "templateName": "John Electric",
            "name": "John Electric LLC",
            "phoneNumber": "23499089727",
            "email": "john1201@gmail.com"
			....
        }
    ]
}

```

***Note: Use the "contactUID" attribute value for the receiver accountUID.***


### **>> Get the auth access token using the "API key" and "API secret" provided by the financial institution**


[POST /auth/realms/{{TENANT-CODE}}/protocol/openid-connect/token/)]

**Auth Request**

```yaml Before
curl -X POST [URL] 
-H "Content-Type: application/x-www-form-urlencoded" 
-H 'Authorization: Basic [Base64(apikey:apisecert)]' 
-d 'grant_type=client_credentials'


```

**Auth Response**

```yaml Before
{
 "access_token": "",
 "expires_in": 14400,
 "refresh_expires_in": 1800,
 "refresh_token":"",
 "token_type": "bearer",
}
```
***Note: Use access_token to call Finzly Connect APIs.***

