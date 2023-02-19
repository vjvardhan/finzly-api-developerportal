---
title: Wired Transactions
---

## **Wire Transactions**
<!--
![image info](./images/Wired.png)
<br></br>
-->

### **Wire Transactions**

Finzly Connect APIs support following business function code for the Fedwire payments.

|**Business Function Codes**|**Description**|
| :- | :-: |
| CTR | Customer or Corporate Credit Transfer (Where Beneficiary is a Customer - Consumer/Corporate)|
| CTP | Customer Transfer Plus (Where Beneficiary is a Customer - Consumer /Corporate with Additional remittance information) |
| DRC | Customer or Corporate Drawdown Request|
| DRW | Drawdown Payment |


### **Payment Status Updates**
  - Payment Status Notification for every event on the wire life cycle will be notified. This will be applied for both outgoing and incoming payments.
  - Validation Failed - Fedwire Payment with the Exception status will be notified.
  - OFAC Review/Reject - Fedwire Payment with OFAC compliance Exception will be notified.
  - Memo Post Status - Fedwire Payment with memo post status failure will be notified.
  - Processed - Notification back to the Customer on payment Processing.

### **Drawdown Initiation**
-  Capability to initiate a Drawdown request for both Customer and as well as for the Bank for their treasury Funds/Fed Transfers.
  - Drawdown initiation is possible for customer using the open Banking API and Bulk Files.
  - Every Drawdown request initiated will be received as a Separate drawdown payment linking the original payment. 

## **Notifications**
Fedwire Incoming payment notification will be triggered with a source of Webhook notification. Customers can configure to receive these notifications. All the Inbound wire can be transmitted with a Raw Wire File message file received from Fed through the FTP source. Customer can configure an Inbound FTP account to receive the actual raw messages.

Inbound Drawdown request are triggered with E-mail notifications for the Bank to take an action on the drawdown requests which does not match based on the agreement set by the customer as part of the Finzly positive rules feature. This notification will be user friendly action for Bank to take an action on the Pending request which does not match to automatically create a drawdown payment out.