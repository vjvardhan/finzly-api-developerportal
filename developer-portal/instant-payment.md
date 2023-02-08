---
title: Instant Payment  
---

## How to initiate an instant payment

One can initiate an instant payment request using Finzly Connect Payment API using the following simple steps. The single payment API supports the payment origination for the various payment rails such as ACH, Fedwire, SWIFT, and Instant Payments based on speed preference.


### **Step 1: Identify the sender’s account unique identifier.**

If the sender’s bank account is already onboarded in the BankOS CRM system. Then execute the below API to get the account UID (Unique Identifier) associated with the bank account, if it is not set up in the BankOS CRM system then you can ignore this step.

[GET - {{URL}}/customers/{{customer_UID}}/accounts?accountNumber={{account_Number}}](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/createCreditPaymentV3/)

Where: 
- **customer_UID:** This is the unique ID assigned to the customer.
- **account_Number:** This is the account number.


**Bank Account Response:**

```yaml Before
{
    "status": "Success",
    "code": null,
    "message": null,
    "data": {
        "accountUID": 58,
        "name": "PWC DDA Account 1",
        "accountNumber": "****0001",
        "fboAccountNumber": "",
        "type": "DEPOSIT",
        "subType": "CHECKING",
        "systemOfRecords": "Other Core",
        "balanceType": "Available",
        "ledgerBalance": null ……
    }
} 

```

**Note: Get the bank account value from the “contactUID” attribute.**


### **Step 2: Identify the receiver’s account unique identifier.**

If the receiver’s bank account is already onboarded in the BankOS CRM system. Then execute the below API to get the account UID (Unique Identifier), if it is not set up in the BankOS CRM system then you can ignore this step

[GET - {{URL}}/customers/{{customer_UID}}/contacts?accountNumber={{account_Number}}](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/searchCustomerContactsV2/)

Where: 
- **customer_UID:** This is the unique ID assigned to the customer.
- **account_Number:** This is the account number.

**Bank Account Response:**  

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
            "externalReferenceId": null,
            "contactUID": "29",
            "templateName": "John Electric",
            "name": "John Electric LLC",
           "phoneNumber": "23499089727",
            "email": "john1201@gmail.com"
        }
    ]
}

```

***Note: Get the bank account value from the “contactUID” attribute.***



### **Step 3: Get the auth token using the “API key” and “API secret” provided by the financial institution.**

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


### **Step 4: Execute an instant payment request.** 

Prepare the payment request object using the sender and receiver account UID along with the speed associated with the instant payment that is **“Instant”**.

```yaml Before

{
	"externalReferenceId": "PaymentRef100",
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



