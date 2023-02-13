---
title: Instant Payments
---


## **Instant Payments**

Instant payments settle in real time providing speed and immediacy for fund availability, creating a lot of value and convenience to consumers and businesses. 

In the US, there are two instant payment networks.
- RTP that settles on the Real-Time Payments network, facilitated by The Clearing House.
- FedNow that settles on the FedNow network, facilitated by The Federal Reserve Board

It is important to note that while instant payments are also enabled by card providers, they are more expensive than RTP and FedNow payments. Finzly offers instant payments from one bank account to another bank account using both RTP and FedNow networks, depending on the sending/receiving banks’ connectivity. 

For payments to be sent in real-time, the recipient banks must be able to receive instant payments either on RTP or FedNow, failing which the payments will be routed through the next fastest network or depending on the bespoke routing rules set up for the workflow.

### **Key features of Finzly Connect instant payment API:**
- Access to both RTP and FedNow networks with a single API
- ISO20022 format messaging
- Secure transactions with traceability for ongoing transactions
- Automated reconciliation and error handling 
- Initiate, Track and Search for payments
- Access to network participant list and participation details
- Fall back options to route payments depending on receiving banks’ participation in instant payment networks

<!-- ![image info](./images/service.png)

<br>

![image info](./images/transaction.png)

<br> -->

### **Use case in action:**

An insurance platform wants to settle claims to policyholders instantaneously using Finzly Connect APIs.
1. Use Finzly Connect’s  Ledger-as-a-service to set up policy holders on virtual accounts 
2. Initiate instant claim reimbursements for policy holders by initiating instant payments through our API
3. Allow policy holders to receive reimbursements instantly into their accounts
4. Track the status change for the reimbursements processed on the platform
5. Update claim reimbursement status in your platform for each status change, delivering exceptional customer experience