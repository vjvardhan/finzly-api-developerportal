---
title: ACH Transaction
---

## **ACH Processing**

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

Standard ACH files are transmitted at the following times.

---
title: ACH Positive Pay
---

## **ACH Positive Pay** 

Positive Pay services allow the bank, and the bank's clients (via APIs or Finzly Treasury Experience) to enable rules to determine if ACH debits should be paid against the receiver's bank account. The service allows users to review all incoming debits before they’re cleared to pay against their account or rejected and returned. The bank can define a “decision cutoff” time, along with a default decision to pay or reject any debits that have not been decisioned.

## **Block List** 

The Block List is a service which provides the user the ability to identify specific ACH debit entries to be "stopped" and either returned automatically or to be manually decisioned as to whether the item should be returned or posted.

---
title: Prefund vs Non-Prefund
---



## **Prefund vs Non-Prefund** 

To support the ACH Prefunding requirements for ACH Credits, Payment Galaxy provides a Prefunding capability, which causes the originator's offset account to be debited on the day their ACH file is processed, instead of waiting until the effective date of the ACH credits. Prior to routing the ACH credits to the FedACH network, the system will verify sufficient funds are available in the originator's account to fund the ACH credits. Alternatively, prefunding can be disabled, allowing for settlement to the originator's account on the effective date. For non-prefunded originators, you can assign exposure limits to monitor the overall amount of exposure to the bank.

---
title: Bulk Upload
---



## **Bulk Upload** 

Finzly system supports the ACH bulk payment processing in a NACHA format via FTP channel. The bank can create an FTP account to process the ACH bulk file in a Nacha format. The solution provided two types of FTP account.

**Customer:** To be used by the corporate or Fintech to upload the bulk payments 

**Channel:** To be used by the bank’s system to upload the payments in bulk associated with the multiple customers.

### **Summary** 

NACHA has various rules around each transaction processing. ACH is very complex to develop than other payment rails, but Finzly has made them simple with APIs. Finzly also offers file uploads of NACHA formatted files and returns NACHA formatted response files.
