---
title: Instant Payment  
---

## How to initiate an instant payment

You can initiate an instant payment using the simple instructions defined below. We have exposed a single Finzly Connect API that supports the initiation of any types of payment using the speed preference choosen by the user. Once the API is executed using speed associated with the instant payment rail, the payment hub system applies the smart routing rules to process and settle the payment via FedNow or RTP payment network.


### **Sceanrio 1: Execute an instant payment request [Sender and Receiver already exist in the BankOS system]**

[POST /payments/creditrequest](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/paymentapi/operation/createCreditPayment/)

**HTTP Method: POST**

Prepare the instant payment request object by providing the simple payment instructions such as sender, receiver, payment amount, notes and set the speed as **"Instant"**.


```yaml Before

{
	"externalReferenceId": "paymentref100",
	"paymentAmount": 100,
	"paymentCurrency": "USD",
	"speed": "Instant",
	"paymentNotes": "Notes",
	"sender": {
		"accountUID": "58"
	},
	"receiver": {
		"accountUID": "29"
	}
}
```


### **Sceanrio 2: Execute an instant payment request [Sender and Receiver does exist in the BankOS system]**

[POST /payments/creditrequest](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/paymentapi/operation/createCreditPayment/)

**HTTP Method: POST**

Prepare the instant payment request object by providing the simple payment instructions such as sender, receiver, payment amount, notes and set the speed as **"Instant"**.


```yaml Before

{
	"externalReferenceId": "paymentref101",
	"paymentAmount": 100,
	"paymentCurrency": "USD",
	"speed": "Instant",
	"paymentNotes": "Notes",
	"sender": {
		"accountNumber": "112266",
        "accountType": "Deposit",
        "subAccountType": "Checking or Saving",
        "name": "Sender Name",
        "bankIdType": "NID",
        "bankId": "Bank routing number",
        "entityType": "Consumer or Corporate",
        "address": {
            "addressLine1": "Sender Address 1",
            "addressLine2": "Sender Address 2",
            "city": "Sender City Name",
            "state": "Sender State Name",
            "postalCode": "Sender Postal Code",
            "countryCode": "Country Code"
        },
        "phone": "Phone Number (if any)",
        "email": "Email Address (if any)"
	},
	"receiver": {
		"accountNumber": "Receiver account number",
        "accountType": "Deposit",
        "subAccountType": "Checking or Savings",
        "name": "Receiver Name",
        "accountCurrency": "USD",
        "address": {
            "addressLine1": "Receiver Address 1",
            "addressLine2": "Receiver Address 2",
            "city": "Receiver City Name",
            "state": "Receiver State Name",
            "postalCode": "Receiver Postal Code",
            "countryCode": "Country Code"
        },
        "phone": "Phone Number (if any)",
        "email": "Email Address (if any)"
        "bank": {
            "name": "Bank Name",
            "countryCode": "US",
            "bankIdType": "NID",
            "bankId": "Routing Number",
			"address": {
				"addressLine1": "Receiver Address 1",
				"addressLine2": "Receiver Address 2",
				"city": "Receiver City Name",
				"state": "Receiver State Name",
				"postalCode": "Receiver Postal Code",
				"countryCode": "Country Code"
			}
        }
	}
}
```

**Payment Speed Details**

The user can define the speed of money movement as part of their preference to execute the payment. The cost of the payment depends on the sponsor bank, while the speed is setup using different parameters that correspond to different payment rails that determine how quickly money can be moved.

|**Speed**|**Speed Description**|
| :- | :- |
|Instant|RTP or FedNow based upon the smart routing rules configuration|



### **How to identify the sender unique identifier id (accountUID)**

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


### **How to Identify the receiver unique identifier id (accountUID)**

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
            "email": "john1201@gmail.com" ....
        }
    ]
}

```

***Note: Use the "contactUID" attribute value for the receiver accountUID.***

### **Get the auth token using the "API key" and "API secret" provided by the financial institution.**


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










