---
title: Fedwire
---



## **Fedwire** 

Fedwire Funds Services (Fedwire) is a real-time gross settlement transfer system that allows participating financial institutions to send and receive same-day fund transfers. Federal Reserve operates the Fedwire payment network, typically used to process high value payments or payments that are required to be delivered faster, generally in a matter of hours. Wire APIs are increasingly being used to build cash management applications and ESCROW services for real estate, broker-dealer payments and many more B2B use cases.

### **Key features of Finzly Connect wire API:**

- Secure transactions with traceability for ongoing transactions
- Complete automation of wire payment initiation
- Automated reconciliation and error handling 
- Track and search for wire payments
- ISO20022 message format compatible
- Ability to send both international and domestic wires

### **Use case in action:**

A corporate treasurer wants to make high-value, time-sensitive payments through his AR/AP platform to his suppliers. With the API integration to the corporate AR/AP platform through Finzly Connect APIs, he can enjoy a seamless payment experience embedded into his AR/AP platform, with the ability to update the payment status in real-time into the platform. 
	1. Initiation of wire on their AR/AP platform
	2. Status update of payments at various stages of processing 
	3. Update payment status in payroll processing platform for each status change

### **Business codes**

Finzly Connect supports the following categories of Fedwire payment business codes.

|**Business Codes**|**Description**|
| :- | :- |
|CTR|Customer or Corporate Credit Transfer (Where Beneficiary is a Customer - Consumer/Corporate)|
|BTR|Bank to Bank Transfer (where Beneficiary is Bank)|
|CTP|Customer Transfer Plus (Where Beneficiary is a Customer - Consumer /Corporate with Additional remittance information)|
|DRC|Customer or Corporate Drawdown Request|
|DRB|Bank to Bank Drawdown Request|
|DRW|Drawdown Payment|
|SVC|Service message|

### **Drawdowns**
- Drawdown initiation is possible using the open Banking API and Bulk Files
- Every Drawdown request initiated will be received as a separate drawdown payment linking the original payment

### **Cut-off times**

The Fedwire Funds Service business day begins at 9:00 p.m. Eastern Time (ET) on the preceding calendar day and ends at 7:00 p.m. ET, Monday through Friday, excluding designated holidays. However, wire payments can be scheduled anytime as long as it is to be processed in the future

### **Payment Notifications**

Clients can enjoy notifications about the status of the wire payments if they subscribe to webhooks. All the inbound wires can be transmitted with a raw wire message file received from Fed through the FTP source. Customers can configure an inbound FTP account to receive the actual raw messages.

Inbound Drawdown requests are triggered with E-mail notifications to the bank to take an action depending on positive rules set up by the customer.

Payment Status Notification for every event on the wire life cycle will be notified. This will be applied for both outgoing and incoming payments.
- Validation Failed - Fedwire Payment with the Exception status will be notified
- OFAC Review/Reject - Fedwire Payment with OFAC compliance Exception will be notified
- Memo Post Status - Fedwire Payment with memo post status failure will be notified
- Processed - Notification back to the Customer on payment processing

<!-- Fedwire Funds Services (Fedwire) is a real-time gross settlement transfer system that allows participating financial institutions to send and receive same-day fund transfers. Federal Reserve operates the FEDWIRE payment network and is typically used to process high value payments or the payments that are required to be delivered faster, typically within an hour. Note: There could be delay due to compliance and other bank policies.

The Fedwire Funds Service is a credit transfer service. Participants originate funds transfers by instructing a Federal Reserve Bank to debit funds from its own account and credit funds to the account of another participant. Participants may originate funds transfers online, by initiating a secure electronic message, or offline, via Teller, Phone-in.

Fedwire funds are sent directly from the originator's bank account to the receiver's bank account. Wires are instant, but the fee can be a configurable data for both sender and receiver. The transaction is permanent and irrevocable with an option to request for Reversal (Return of Funds).

FEDWIRE is a message-oriented payment system. Each payment travels in a single message and is gross settled, whereas ACH payments are net settled. 

Fedwire operates weekdays, from 9 p.m. the prior calendar day, to 7 p.m. Eastern Time. The system is closed during weekends and federal holidays, with the exception being that service for Mondays are operational from 9 p.m. on the preceding Sunday. Though operational until 7 p.m. ET, the deadline for initiating a payment for a bank’s customer, is 6 p.m. ET.

Reversals - Cut off time for Reversals are separately maintained as configurable property. Any Reversal after that cut off will not be eligible and will have to reverse the next business day  -->
