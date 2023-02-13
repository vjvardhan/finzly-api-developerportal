---
title: Wired Organization
---



## **Wire Origination**

![image info](./images/Wired.png)
<br></br>

Fedwire Funds service supports the following origination gateways for processing through BankOS 

<svg width="12" height="12" x="0" y="0" viewBox="0 0 32 32"> <g transform="matrix(-1,-1.2246467991473532e-16,1.2246467991473532e-16,-1,32,32)"><path d="M16 1a15 15 0 1 0 15 15A15.017 15.017 0 0 0 16 1zm2.707 20.293a1 1 0 1 1-1.414 1.414l-6-6a1 1 0 0 1 0-1.414l6-6a1 1 0 0 1 1.414 1.414L13.414 16z" fill="#003c90" data-original="#000000" class=""></path></g></svg> API – Finzly Connect APIs
  - Supports the initiation of
  - Customer or Corporate credit transfer 
  - Customer Transfer Plus 
  - Customer or Corporate Drawdown Request

<svg width="12" height="12" x="0" y="0" viewBox="0 0 32 32"> <g transform="matrix(-1,-1.2246467991473532e-16,1.2246467991473532e-16,-1,32,32)"><path d="M16 1a15 15 0 1 0 15 15A15.017 15.017 0 0 0 16 1zm2.707 20.293a1 1 0 1 1-1.414 1.414l-6-6a1 1 0 0 1 0-1.414l6-6a1 1 0 0 1 1.414 1.414L13.414 16z" fill="#003c90" data-original="#000000" class=""></path></g></svg> Web - Online Digital Treasury Portal (CashOS)

- Supports the initiation of domestic wire transfer
- This will be defined based on the Processing speed as Express (Configurable) and Fees to be applied.

<svg width="12" height="12" x="0" y="0" viewBox="0 0 32 32"> <g transform="matrix(-1,-1.2246467991473532e-16,1.2246467991473532e-16,-1,32,32)"><path d="M16 1a15 15 0 1 0 15 15A15.017 15.017 0 0 0 16 1zm2.707 20.293a1 1 0 1 1-1.414 1.414l-6-6a1 1 0 0 1 0-1.414l6-6a1 1 0 0 1 1.414 1.414L13.414 16z" fill="#003c90" data-original="#000000" class=""></path></g></svg>  Branch - Teller Application (Wire Room) 

- Supports the initiation of Wire from branch using the teller application with an option as
  - Walk-in 
  - Phone-in

<svg width="12" height="12" x="0" y="0" viewBox="0 0 32 32"> <g transform="matrix(-1,-1.2246467991473532e-16,1.2246467991473532e-16,-1,32,32)"><path d="M16 1a15 15 0 1 0 15 15A15.017 15.017 0 0 0 16 1zm2.707 20.293a1 1 0 1 1-1.414 1.414l-6-6a1 1 0 0 1 0-1.414l6-6a1 1 0 0 1 1.414 1.414L13.414 16z" fill="#003c90" data-original="#000000" class=""></path></g></svg>  Bulk uploads 

- Supports the initiation of wire with an option from Bulk File processing
  - Fedwire message upload 
    - This will be based on the actual raw Fedwire message structure.
    - Multiple Fedwire message can be uploaded in a File

<svg width="12" height="12" x="0" y="0" viewBox="0 0 32 32"> <g transform="matrix(-1,-1.2246467991473532e-16,1.2246467991473532e-16,-1,32,32)"><path d="M16 1a15 15 0 1 0 15 15A15.017 15.017 0 0 0 16 1zm2.707 20.293a1 1 0 1 1-1.414 1.414l-6-6a1 1 0 0 1 0-1.414l6-6a1 1 0 0 1 1.414 1.414L13.414 16z" fill="#003c90" data-original="#000000" class=""></path></g></svg>   Finzly CSV

- This is customed CSV formatted file for processing the Fedwire payments with required information as
  - Sender (Originator details) 
  - Sender A/c o Receiver (Beneficiary details) 
  - Receiver A/c 
  - Additional Notes
- Finzly CSV supports the following Business Function code
  - Customer or Corporate credit transfer 
  - Customer or Corporate Drawdown Request


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