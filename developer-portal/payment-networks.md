---
title: Finzly API Payment Networks
---

# **Payment Networks**

In this section, we’ll talk about the different payment networks Finzly APIs support.

- ACH (Automated Clearing House)
- WIRES
- FEDNOW (Fedwire Funds Services)
- RTP 
- International Payments

### **ACH** 

ACH (Automated Clearing House) is the most popular, and highly used payment network that was first launched in [xxxx]. ACH payments are exchanged in NACHA formatted files. NACHA sets the rules and guidelines for the processing of ACH payments. After the power of RESTful APIs were proved to be critical for a connected e-commerce and treasury, the need to offer ACH payments via REST API has become critical for the success of banks. 

**ACH Terminologies** 

While ACH payments are cheaper compared to other payment networks, they have most the complexity than other payment rails, as ACH has evolved over several decades to support various use cases of the industry.

**Files & Batches**

Each payment is created as a payment entry, and the entries are grouped in batches and the batches are grouped in a file. Each file and batch may be balanced or unbalanced. 

**Balanced & Unbalanced Files**

In a balanced file, the outbound debits and credits are offset with a customer’s DDA account entry. In an unbalanced file, the bank would offset it with the customer’s default account. 

**SEC Codes**

Each payment entry must be categorized under one of the several Service Entry Class Codes, aka SEC Codes. Finzly supports all the SEC Codes as listed below 



|**SEC Code**|**Description**|**Use** |**Debit / Credit**|**Consumer / Corporate** |
| :- | :-: | :-: | :- | :- |
|ARC|Accounts Receivable Entries|A single ACH debit used by originator for the conversion of an eligible source document received via the U.S. mail or delivery service; at a lockbox location; or in person at a manned location for the payment of a bill.|Debit|Consumer to Corporate|
|ACK|ACH Payment Acknowledge |RDFI to acknowledge the receipt of ACH credit payments originated using the CCD formats|Non-Monetary|N/A|
|ADV|Automated Accounting Advice|identifies automated accounting advice of ACH accounting information in machinereadable format to facilitate the automation of accounting information for participating DFIs |Non-Monetary |N/A|
|ATX|Financial EDI Acknowledgment|RDFI to acknowledge the receipt of ACH credit payments originated using the CTX formats|Non-Monetary|N/A|
|BOC|Back Office Conversion|A single ACH debit initiated by an originator based on an eligible source document provided at the point-of-purchase or at a manned bill payment location for subsequent conversion during back-office conversion. |Debit|Consumer to Corporate|
|CCD|Corporate Credit or Debit|A single or a recurring ACH credit or debit originated to a corporate account. They are commonly used by Originators to pay vendors, concentrate funds from outlying accounts (cash concentration), to fund payroll, petty cash, or other disbursement accounts.|Credit / Debit/ Nonmonetary|Corporate to Corporate|
|CIE|Customer Initiated Entries|A credit entry initiated by consumer through a bill payment service provider to pay bills. |Credit|Consumer to Corporate|
|CTX|Corporate Trade Exchange|A single or a recurring ACH credit or debit originated to a corporate account that supports up to 9,999 addenda records. They are commonly used in trading partner relationships because a full ANSI ASC X12 message or payment-related UN/EDIFACT information can be sent with the CTX entry.|Credit / Debit/ Nonmonetary|Corporate to Corporate|
|IAT|International ACH Transaction |An Entry that is part of a payment transaction involving a financial agency’s office that is not located within the territorial jurisdiction of the United States.|Credit / Debit|Corporate to Consumer/|
|POP|Point of Purchase|A single ACH debit initiated by an originator based on an eligible source document provided at a point-of-purchase or manned bill payment location. |Debit|Corporate to Consumer/|
|POS|Point of Sale|Initiated at an electronic terminal using merchant issued physical card or other access device|Debit|Consumer|
|PPD|Pre-arranged Payment or Deposit|A single or a recurring ACH credit or debit sent by an originator to a consumer account to make or collect a payment, where authorization is obtained in writing. |Credit / Debit|Corporate to Consumer|
|RCK|Re-presented Check Entries|Originators can re-present a check that has been processed through the check collection system as a paper or image item, and returned because of insufficient or uncollected funds|Debit|Corporate to Consumer|
|TEL|Telephone Initiated Entries|A single or a recurring ACH debit that occurs when the consumer’s authorization for a transfer of funds is received orally via the telephone. |Debit|Corporate to Consumer|
|WEB|Internet-Initiated/Mobile Entries|Credit WEB Entries: A Person-to-Person entry transmitted on behalf of one natural person to another natural person, or between accounts belonging to the same natural person. <br><br>Debit WEB Entries: ACH entry initiated according to an authorization obtained via the internet or a wireless network (e.g. mobile device) except for an oral authorization via a telephone call.|Credit / Debit|Corporate to Consumer|
|DNE|Death Notification Entry|Federal Govt. Agency Use Only |Non-Monetary|Consumer|

***Note: Finzly payment hub system support all above sec codes from RDFI perspective. However, from the ODFI perspective the following sec codes are supported BOC, CCD, CIE, CTX, IAT, POP, POS, PPD, TEL and WEB.***

**Addenda Record** 

Each payment entry carries the additional information required to process the payment, and these addenda records are different for various SEC Codes.

**ODFI** 

The financial institution that originates or sends the payment file to FED is called Originating Depository Financial Institution. 

**RDFI** 

The financial institution that receives the payment file from FED is called Receiving Depository Financial Institution.

**ACH Transactions**

**Credit Request**

Credit Request allows ODFI to send a payment to RDFI. RDFI upon receiving the credit request would  either accept the payment and credit its customer or return the payment. 

**Debit Request**

Debit Request allows ODFI to debit request to RDFI. RDFI upon receiving the debit request would either accept the request and debit its customer or return the request.

**Notice of Change**

In case the receiving party’s information is changed for a Credit or Debit request, RDFI may send Notice of Change (NOC) to ODFI.

**Returns**

When the RDFI returns the credit or debit request, the ODFI may accept the return or dishonor the return.




|**Return Code**|**Return Title**|**Return Description**|
| :- | :- | :- | 
|R01|Insufficient Funds|The available and/or cash reserve balance is not sufficient to cover the dollar value of the debit Entry.|
|R02|Account Closed|A previously active account has been closed by action of the customer or the RDFI|
|R03|No Account/ Unable to Locate|The account number structure is valid and it passes the Check digit validation, but the account number does not correspond to the individual identified in the Entry, or the account number designated is not an existing account|
|R04|Invalid Account Number Structure|The account number structure is not valid|
|R05|Unauthorized Debit to Consumer Account Using Corporate SEC Code | CCD or CTX debit Entry was transmitted to a Consumer Account of the Receiver and was not authorized by the Receiver|
|R06|	Returned per ODFIs Request | The ODFI has requested that the RDFI return an Erroneous Entry.|
|R07|Authorization Revoked by Customer|The RDFIs customer (the Receiver) revoked the authorization previously provided to the Originator for this debit Entry.|
|R08|Payment Stopped|The Receiver has placed a stop payment order on this debit Entry|
|R09|Uncollected Funds|A sufficient ledger balance exists to satisfy the dollar value of the transaction, but the available balance is below the dollar value of the debit Entry|
|R10|Customer Advises Not Authorized, Improper, Ineligible, or Part of an incomplete transaction|The RDFI has been notified by the Receiver that the Entry is unauthorized, improper, ineligible, or part of an incomplete transaction.|
|R11|Customer Advises entry not in accordance with the terms of Authorization|Error or defect in payment between originator and receiver|
|R12|Account Sold to Another DFI| A financial institution received an Entry to an account that was sold to another financial institution.|
|R14|Representative Payee Deceased or Unable to Continue in that Capacity to continue in that capacity| The representative payee is either deceased or unable to continue in that capacity. The beneficiary is NOT deceased.|
|R15|Beneficiary or Account Holder (Other Than a Representative) | (1) The beneficiary is deceased, or (2) The account holder is deceased.|
|R16|Account Frozen/Entry Returned per OFAC Instruction|OFAC has instructed the RDFI to return the Entry|
|R17|File Record Edit Criteria |An RDFI would use R17 to return an entry that does not have a valid account number and the RDFI believes the entry was initiated under questionable circumstances. |
|R20|Non-Transaction Account|ACH Entry to a Non-Transaction Account|
|R21|Invalid Company Identification |The identification number used in the Company Identification Field is not valid|
|R22|Invalid Individual ID Number|The Receiver has indicated to the RDFI that the number with which the Originator was identified is not correct.|
|R23|Credit Entry Refused by Receiver|Any credit Entry that is refused by the Receiver may be returned by the RDFI. |
|R24|Duplicate Entry|The RDFI has received what appears to be a duplicate entry; i .e., the trace number, date, dollar amount and/or other data matches another transaction. |
|R26|Mandatory Field Error |Improper information in one of the mandatory fields|
|R29|Corporate Customer Advises Not Authorized|he RDFI has been notified by the Receiver (nonconsumer) that the Originator of a given transaction has not been authorized to debit the Receiver account.|
|R31|Permissible Return Entry (CCD and CTX only) |The RDFI may return a CCD or CTX Entry that the ODFI agrees to accept.|
|R61|Misrouted Return|The financial institution preparing the Return Entry (The RDFI of the original Entry) has placed the incorrect Routing Number in the Receiving DFI Identification field. |
|R67|Duplicate Return |The ODFI has received more than one Return for the same Entry.|
|R68|Untimely Return|The Return Entry has not been sent within the timeframe established by these Rules.|
|R69|Field Error(s)|One or more of the field requirements are incorrect|
|R70|Permissible Return Entry Not Accepted/ Return Not Requested by ODF |The ODFI has received a Return Entry identified by the RDFI as being returned with the permission of, or at the request of, the ODFI, but the ODFI has not agreed to accept the Entry or has not requested the return of the Entry.|
|R71|Misrouted Contested Dishonored Return|The financial institution preparing the dishonored Return Entry (the ODFI of the original Entry) has placed the incorrect Routing Number in the Receiving DFI Identification field. |
|R72|Untimely Dishonored Return|The dishonored Return Entry has not been sent within the designated timeframe.|
|R73 |Timely Original Return|The RDFI is certifying that the original Return Entry was sent within the timeframe designated in these Rules. |
|R74|Corrected Return |The RDFI is correcting a previous Return Entry that was dishonored using Return Reason Code R69 (Field Errors) because it contained incomplete or incorrect information. |
|R75|Return Not a Duplicate|The Return Entry was not a duplicate of an Entry previously returned by the RDFI.|
|R76|No Errors Found |The original Return Entry did not contain the errors indicated by the ODFI in the dishonored Return Entry. |


**On-us Transactions** 

On-us transactions in ACH is when a bank’s customer initiates ACH transfers for which the bank is both ODFI and RDFI. For such transactions, bank can settle within its ledger without having to clear thru ACH network.

**Same-day and Standard ACH** 

ACH payments are usually processed with 2 days settlement, which means if a payment is initiated, it would take two business days for the payment to get credited in the customer account. In 20xx, NACHA required the clearing houses to support same-day ACH payments to allow same day processing and settlement. For some weird reason, several financial institution’s ACH system does not support same day ACH and can only process regular ACH payments.

**Cutoff Times** 

The Federal Reserve processes the files on all bank working days from x:00 to x:00. Same day ACH files are transmitted at the following times

Standard ACH files are transmitted at the following times…

**ACH Positive Pay** 

Positive Pay services allow the bank, and the bank's clients (via APIs or Finzly Treasury Experience) to enable rules to determine if ACH debits should be paid against the receiver's bank account. The service allows users to review all incoming debits before they’re cleared to pay against their account or rejected and returned. The bank can define a “decision cutoff” time, along with a default decision to pay or reject any debits that have not been decisioned.

**Block List** 

The Block List is a service which provides the user the ability to identify specific ACH debit entries to be "stopped" and either returned automatically or to be manually decisioned as to whether the item should be returned or posted.


**Prefund/Non-Prefund** 

To support the ACH Prefunding requirements for ACH Credits, Payment Galaxy provides a Prefunding capability, which causes the originator's offset account to be debited on the day their ACH file is processed, instead of waiting until the effective date of the ACH credits. Prior to routing the ACH credits to the FedACH network, the system will verify sufficient funds are available in the originator's account to fund the ACH credits. Alternatively, prefunding can be disabled, allowing for settlement to the originator's account on the effective date. For non-prefunded originators, you can assign exposure limits to monitor the overall amount of exposure to the bank.

**ACH Bulk Upload** 

Finzly system supports the ACH bulk payment processing in a NACHA format via FTP channel. The bank can create an FTP account to process the ACH bulk file in a Nacha format. The solution provided two types of FTP account.

**Customer:** To be used by the corporate or Fintech to upload the bulk payments 

**Channel:** To be used by the bank’s system to upload the payments in bulk associated with the multiple customers.

**Summary** 

NACHA has various rules around each transaction processing. ACH is very complex to develop than other payment rails, but Finzly has made them simple with APIs. Finzly also offers file uploads of NACHA formatted files and returns NACHA formatted response files.

### **FEDWIRE** 

Fedwire Funds Services (Fedwire) is a real-time gross settlement transfer system that allows participating financial institutions to send and receive same-day fund transfers. Federal Reserve operates the FEDWIRE payment network and is typically used to process high value payments or the payments that are required to be delivered faster, typically within an hour. Note: There could be delay due to compliance and other bank policies.

The Fedwire Funds Service is a credit transfer service. Participants originate funds transfers by instructing a Federal Reserve Bank to debit funds from its own account and credit funds to the account of another participant. Participants may originate funds transfers online, by initiating a secure electronic message, or offline, via Teller, Phone-in.

Fedwire funds are sent directly from the originator's bank account to the receiver's bank account. Wires are instant, but the fee can be a configurable data for both sender and receiver. The transaction is permanent and irrevocable with an option to request for Reversal (Return of Funds).

FEDWIRE is a message-oriented payment system. Each payment travels in a single message and is gross settled, whereas ACH payments are net settled. 

Fedwire operates weekdays, from 9 p.m. the prior calendar day, to 7 p.m. Eastern Time. The system is closed during weekends and federal holidays, with the exception being that service for Mondays are operational from 9 p.m. on the preceding Sunday. Though operational until 7 p.m. ET, the deadline for initiating a payment for a bank’s customer, is 6 p.m. ET.

Reversals - Cut off time for Reversals are separately maintained as configurable property. Any Reversal after that cut off will not be eligible and will have to reverse the next business day 

**Business Codes**

FEDWIRE payments are categorized into the following business codes. 

- CTR - Customer or Corporate Credit Transfer (Where Beneficiary is a Customer - Consumer 

/Corporate)

- BTR - Bank to Bank Transfer (where Beneficiary is Bank)
- CTP - Customer Transfer Plus (Where Beneficiary is a Customer - Consumer /Corporate with Additional remittance information) 
- DRC - Customer or Corporate Drawdown Request
- DRB - Bank to Bank Drawdown Request
- DRW - Drawdown Payment 
- SVC - Service message

### **Wire Origination**

Fedwire Funds service supports the following origination gateways for processing through BankOS 

` `- API – Finzly Connect APIs

- ` `Supports the initiation of
  - Customer or Corporate credit transfer 
  - Customer Transfer Plus 
  - Customer or Corporate Drawdown Request

` `- Web - Online Digital Treasury Portal (CashOS)

- Supports the initiation of domestic wire transfer
  - ` `This will be defined based on the Processing speed as Express (Configurable) and Fees to be applied.

\-  Branch - Teller Application (Wire Room) 

- Supports the initiation of Wire from branch using the teller application with an option as
  - Walk-in 
  - Phone-in

\-  Bulk uploads 

- Supports the initiation of wire with an option from Bulk File processing
  - ` `Fedwire message upload 
    - This will be based on the actual raw Fedwire message structure.
    - Multiple Fedwire message can be uploaded in a File

\-   Finzly CSV

- This is customed CSV formatted file for processing the Fedwire payments with required information as
  - Sender (Originator details) 
  - Sender A/c o Receiver (Beneficiary details) 
  - Receiver A/c 
  - Additional Notes
- Finzly CSV supports the following Business Function code
  - Customer or Corporate credit transfer 
  - Customer or Corporate Drawdown Request


### **Payment Status Updates**
  - __Payment Status Notification for every event on the wire life cycle will be notified. This will be applied for both outgoing and incoming payments.__
  - __Validation Failed - Fedwire Payment with the Exception status will be notified.__ 
  - __OFAC Review/Reject - Fedwire Payment with OFAC compliance Exception will be notified.__
  - __Memo Post Status - Fedwire Payment with memo post status failure will be notified.__
  - __### Processed - Notification back to the Customer on payment Processing.__

### **Drawdown Initiation**
- __Capability to initiate a Drawdown request for both Customer and as well as for the Bank for their treasury Funds/Fed Transfers.__
  - Drawdown initiation is possible for customer using the open Banking API and Bulk Files.
  - Every Drawdown request initiated will be received as a Separate drawdown payment linking the original payment. 

### **Notifications**
Fedwire Incoming payment notification will be triggered with a source of Webhook notification. Customers can configure to receive these notifications. All the Inbound wire can be transmitted with a Raw Wire File message file received from Fed through the FTP source. Customer can configure an Inbound FTP account to receive the actual raw messages.

Inbound Drawdown request are triggered with E-mail notifications for the Bank to take an action on the drawdown requests which does not match based on the agreement set by the customer as part of the Finzly positive rules feature. This notification will be user friendly action for Bank to take an action on the Pending request which does not match to automatically create a drawdown payment out.
### **Instant Payments**

While ACH is used for high volume or low value payments, and FEDWIRE is used for faster or high value payments, the new instant payment networks such as RTP and FEDNOW are emerging to enable instant payments that are processed in real-time within seconds and are irrevocable. It is important to note that Debit cards enable instant payments, those transactions are comparatively expensive than RTP or FEDNOW payments and requires a debit card in addition to the bank account. Finzly offers instant payments from a bank account to another bank account via either RTP or FEDNOW, based on the sender and receiver bank’s connectivity. 

While there are other payment networks such as Zelle, Venmo, Cash App enable real-time settlement of funds at user’s accounts, these payment rails operate on top of other clearing networks such as ACH, RTP, FEDNOW or Card networks. 

The following diagram explains the fund flow in FedNow and RTP payment network.

**FedNow:** 

![image info](./images/service.png)

**RTP:**

![image info](./images/transaction.png)

Finzly Connect offers instant payment access and notifications via simple REST API. Develop new financial products such as Point of Sale, QR based invoices, and get paid instantly from your customer’s bank and eliminate card transaction fees.

### **International Payments**

The commerce is now global, and the businesses have to routinely send and receive payments to and from global vendors and customers. Finzly Connect allows making global payments, tracking and payment notifications via API easier.

The domestic payment networks such as ACH, FEDWIRE, RTP and FEDNOW makes interborder settlement easier, but the international payments have more stringent compliance requirements and is more complex than domestic payments.

To process international payments, your bank should either be connected with a correspondent bank who have SWIFT connection, or your bank should have direct SWIFT connectivity. Finzly directly connects with SWIFT to settle and clear international payments for your bank.

Finzly Connect, with a single API, powers you to send international payments to any recipient in the globe and receive payment notifications from your bank account for easy and automatic reconciliation.

