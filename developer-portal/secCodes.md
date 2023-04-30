---
title: SEC Code 
---


## **SEC Codes**

Each payment entry must be categorized under one of the several Service Entry Class Codes, aka SEC Codes. Finzly supports all the SEC Codes as listed below 

|**SEC Code**|**Description**|**Use** |**Debit / Credit**|**Consumer / Corporate** |
| :- | :-: | :-: | :- | :- |
|ARC|Accounts Receivable Entries|A single ACH debit used by originator for the conversion of an eligible source document received via the U.S. mail or delivery service; at a lockbox location; or in person at a manned location for the payment of a bill.|Debit|Consumer to Corporate|
|ACK|ACH Payment Acknowledge |RDFI to acknowledge the receipt of ACH credit payments originated using the CCD formats|Non-Monetary|N/A|
|ADV|Automated Accounting Advice|identifies automated accounting advice of ACH accounting information in machine readable format to facilitate the automation of accounting information for participating DFIs |Non-Monetary |N/A|
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

***Note: Finzly Connects supports all above SEC codes from RDFI perspective. However, from the ODFI perspective the following SEC codes are supported in the platform BOC, CCD, CIE, CTX, IAT, POP, POS, PPD, TEL and WEB.***

**Addenda Record** 

Each payment entry carries the additional information required to process the payment, and these addenda records are different for various SEC Codes.

**ODFI** 

The financial institution that originates or sends the payment file to FED (Federal Reserve Board) is called Originating Depository Financial Institution. 

**RDFI** 

The financial institution that receives the payment file from FED (Federal Reserve Board) is called Receiving Depository Financial Institution.

