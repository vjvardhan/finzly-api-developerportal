---
title: Schedule Recurring Payment  
---

## How to schedule a recurring payment

You the can schedule a recurring payment using the following simple steps


### **Step 1: Identify the sender bank account (funding)  unique identifier (accountUID)**

Execute the below API to get the accountUID (Unique Identifier) associated with the sender bank account.

[GET - {{URL}}/customers/{{customer_UID}}/accounts?accountNumber={{account_Number}}](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/createCreditPaymentV3/)

Where: 
- **customer_UID:** This is the unique ID associated with customer.
- **account_Number:** This is the account number.


**Bank Account Response:**

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
        "balanceType": "Available",
        "ledgerBalance": null ……
    }
} 

```

**Note: Get the sender bank account ID from the "accountUID" attribute.**


### **Step 2: Identify the receiver’s account unique identifier (contactUID)**

Execute the below API to get the contactUID (Unique Identifier) associated with the receiver/beneficiary bank account.

[GET - {{URL}}/customers/{{customer_UID}}/contacts?accountNumber={{account_Number}}](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/searchCustomerContactsV2/)

Where: 
- **customer_UID:** This is the unique ID associated with the customer.
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

***Note: Get the receiver bank account IDF from the “contactUID” attribute.***



### **Step 3: Get the auth token using the "API key" and "API secret" provided by the financial institution.**

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

Prepare the payment request object using the sender and receiver UID along with the speed associated with the payment.

```yaml Before

{
	"externalReferenceId": "PaymentRef100",
	"paymentAmount": 100,
	"paymentCurrency": "USD",
	"speed": "Economy Plus",
	"paymentNotes": "Notes",
	"paymentDate":"2023-05-01"
	"sender": {
		"accountUID": "58"
	},
	"receiver": {
		"accountUID": "29"
	},
	"recurrence": {
		"frequency": "Weekly",
		"payUntil":"NumberOfPayments",
		"numberOfPayments": 10
	}
}

```

Note: Use the recurrence object to schedule a recurring payment

**Payment Recurrence Details**


|**Name**|**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|frequency|request|string|true|Payment recurring frequency can be Daily, Weekly, BiWeekly, Monthly, Quarterly, SemiAnnual, Yearly|
|payUntil|request|string|true|Payment recurring options Cancelled, EndDate, NumberOfPayments|
|numberOfPayments|request|string|false|This is needed only when the payUntil is set to NumberOfPayments|
|endDate|request|string|false|This is needed only when the payUntil is set to EndDate|



**Payment Speed Details**

The speed of the payment defines the user prefrence on the money movement while initiating the payment. The speed preference is based upon the cost and time associated with the payment transaction (defined within the BankOS platform by the bank) for instance speed "Express" is associated with the Fedwire payment rail where the payment will be processed normaly within a day in comparison with the speed "Economy" which is associated with the regular ACH payment rail where the payment will be processed within 2-3 business days.

|**Speed**|**Speed Description**|
| :- | :- |
|Economy|Regular ACH|
|Economy Plus|Same Day ACH|
|Express|Fedwire|
|Instant|RTP or FedNow based upon the configuration|
|SPOT|Spot international payment|
|ON|Same day international payment|
|TN|Next day international payment|
