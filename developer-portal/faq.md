---
title: Finzly API FAQ section 
---

# **Frequently Asked Questions**

- ### **What is Finzly Connect?**

Finzly Connect is the universal payment API for developers to access all the payment rails without worrying about the network and messaging rules.

- ### **What does Finzly Connect do?**

Finzly Connects offers REST API and webhook notifications to access any Finzly-powered bank. Finzly has normalized the payment data and made the payment processing super simple, so a bank customer, whether a fintech, business or an individual, doesn’t have to fret over the messaging rules. A developer can access ACH, Domestic Wires, International Wires, RTP, and FedNow using Finzly Connect and connect to their favorite Finzly Bank.

- ###  **Does Finzly API support Bulk Payment Processing?**

Finzly system supports the ACH bulk payment processing in a NACHA format via the FTP channel. The bank can create an FTP account to process the ACH bulk file in a Nacha format. The solution provided two types of FTP accounts. 

Customer: To be used by the corporate or Fintech to upload the bulk payments 

Channel: To be used by the bank’s system to upload the payments associated with multiple customers. 

NACHA has various rules around each transaction processing. ACH is very complicated to develop than other payment rails, but Finzly has simplified them with APIs. Finzly also offers file uploads of NACHA formatted files and returns NACHA formatted response files.

- ### **How does Finzly API offer instant payment access?**

Finzly Connect offers instant payment access and notifications via simple REST API. Develop new financial products such as Point of Sale, QR based invoices, and get paid instantly from your customer’s bank and eliminate card transaction fees

- ### **How does Fizly Connect secure payment access?**

Our APIs use the oAuth 2.0 authentication protocol to provide secure access. You will use our API keys with grant type “Client Credentials” to fetch an access token. This token is digitally signed and contains access information such as user role mapping. The access token is short-lived (30 sec). To authenticate and authorize your API calls, you must pass the access token in the authorization header with the “bearer” prefix.

- ### **Who should use Finzly APIs?**

Banks, and Fintechs seeking a modern, flexible, API-centric, end-to-end solution to support their BaaS initiatives and become a developer and fintech-friendly bank. 

- ### **How can I test Finzly APIs?**

Users can perform your testing in Sandbox Mode. This mode provides a testing environment that helps you create an account enabled for making Finzly API calls.
