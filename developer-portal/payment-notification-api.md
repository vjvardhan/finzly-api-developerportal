---
title: Finzly Payment Notfication API
---

# **Payment Status Notifications v1.2.0**

Security protocols support basic authentication by Finzly. This API allows third parties and bank customers to receive payment details whenever there is an update to the payment system. Finzly can also share the FinzlyOS public IPs with third parties or bank customers to whitelist at their end for additional security.

Base URLs:

- [https://{tenant}-security-{environment}.{dns}/auth/realms/BANKOS.UAT.SANDBOX.CUSTOMER/protocol/openid-connect/token](about:blank)
  - **tenant** - Tenant Code Default: sandbox
  - **environment** - Environment Name Default: uat
  - **DNS** - DNS Name Default: [finzly.io](http://finzly.io/)

# Payment Notifications
Payment Notification to third parties whenever there is an update to the payment status in the Finzly payment system.

## **notifyPaymentStatus**
**POST /payments**

**HTTP Method: POST**

**Description -** Payment notification details, including payment Id, source reference, and status, are pushed via this webhook whenever there is an update to the payment status.
# Notify payment information to the client or third party.


|Name|In|Type|Required|Description|
| :- | :- | :- | :- | :- |
|body|body|<p>[payment](https://apidocs.finzly.net/dashboard?java=#schemapayment)</p><p></p>|true|none|
