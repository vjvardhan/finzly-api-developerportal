---
title: Payment Webhooks
---

## **Payment Webhooks**
Payment webhook is used to get notified by Finzly bank whenever a payment event happens in your account. Your bank will help you setup a webhook for your accounts. The following events are sent to webhooks.

**Payment Webhooks**

1. Outgoing credit payment 
2. Outgoing debit payment 
3. Incoming payments
4. Incoming drawdowns
5. Incoming debit requests
6. Incoming returns
7. Incoming NOCs
8. Incoming RFPs

|**Attribute**|**Type**|**Restrictions**|**Notes**|
| :-: | :-: | :- | :-: |
|paymentId|integer|none|Payment unique identifier assigned by the system to the payment object.|
|sourceReferenceId|string|none|Unique identifier assigned by th external system to the payment object.|
|paymentStatus|string|none|Payment status such as VALIDATED, VALIDATION_FAILURE, TRANSMITTED, PROCESSED, CANCELLED etc|
|bulkFileName|string|none|Name of the file, if the payment is uploaded from the file to the finzly payment hub system via FTP or API channel.|
|counterParty|string|none|Shortname associated with the legal entity defined in the CRM system.|
|deliveryDate|string(date)|none|Delivery date refers to the date on which payment is settle|
|deliveryMethod|string|none|The delivery method used to setlle the payment such as ACH, WIRE, RTP,FEDNOW, SWIFT, etc.|
|feeAmount|number(decimal)|none|Fee amount|
|paymentDate|string(date)|none|Date on which the payment is originated in the system.|
|channel|string|none|Channel represents the system that originates the payment for example API, TELLER, CASHOS, ONLINE etc.|
|paymentIOType|string|none|Whether the payment is Inbound or Outbound|
|paymentNote1|string|none|Payment notes provided by the external system|
|paymentNote2|string|none|Additional payment notes|
|paymentRemittanceInfo|string|none|Payment remittance information associated with the payment.|
|paymentType|string|none|The payment type associated with the payment such as Same Day ACH, Regular, ACH, WIRE, SWIFT etc.|
|forexContract|string|none|FX contract number associated with the SWIFT payment|
|paymentNocDetails|[Object](https://apidocs.finzly.net/dashboard#schemapayment_paymentnocdetails)|none|The purpose of a NOC to notify you that something about your customer's bank account has changed.|
|paymentNocDetails: nocCode|string|none|Code associated with NOC|
|paymentNocDetails:originalAccountNumber|string|none|Original account number|
|paymentNocDetails: correctedAccountNumber|string|none|Corrected account number|
|paymentNocDetails:originalRoutingNumber|string|none|Original routing number|
|paymentNocDetails: correctedRoutingNumber|string|none|Corrected routing number|
|paymentNocDetails: originalTranCode|string|none|Original tran code|
|paymentNocDetails: correctedTranCode|string|none|Corrected tran code|
|paymentNocDetails: receivedDateTime|string|none|NOC received date and time|
|imad|string|none|It is a unique number given to each Fedwire payment. An IMAD/OMAD number can be used to investigate and track wire transfers.|
|omad|string|none|It is a unique number given to each Fedwire payment. An IMAD/OMAD number can be used to investigate and track wire transfers.|
|receiverAccountNumber|string|none|Account number associated with the receiver|
|receiverAccountType|string|none|Receiver account type|
|receiverAddress1|string|none|Receiver address|
|receiverAmount|number(decimal)|none|Payment amount received by the recipient|
|receiverBankName|string|none|Recipient's bank name|
|receiverBankState|string|none|Recipient's bank state|
|receiverDiscretionaryData|string|none|Receiver's discretionary data|
|receiverEmail|string(email)|none|Receiver's email|
|receiverId|string|none|Receiver unique identifier exist in the Finzly CRM system|
|receiverIdType|string|none|Receiver identifier type|
|receiverName|string|none|Receiver name associated with the payment.|
|originalReceiverName|string|none|The original receiver name received from the payment network for the inbound payment request.|
|receiverPhoneNumber|string|none|Receiver phone number|
|receiverRoutingNumber|string|none|Receiver bank routing number|
|receiverState|string|none|Receiver state|
|receiverTemplateName|string|none|If the template name is associated with the receiver in the payment hub system.|
|receiverType|string|none|Receiver type|
|receiverZip|string|none|Receiver's zipcode|
|ultimateReceiverName|string|none|Ultimate receiver name is associated with the payment.|
|ultimateReceiverAccountNumber|string|none|The ultimate receiver account number|
|ultimateReceiverAddress1|string|none|The ultimate receiver address 1|
|ultimateReceiverAddress2|string|none|The ultimate receiver address 2|
|ultimateReceiverTaxId|string|none|The ultimate receiver tax number|
|ultimateReceiverCity|string|none|The ultimate receiver city|
|ultimateReceiverState|string|none|The ultimate receiver sate|
|ultimateReceiverZip|string|none|The ultimate receiver zipcode|
|ultimateReceiverCountry|string|none|The ultimate receiver country|
|senderAccountNumber|string|none|The sender account number|
|senderAccountType|string|none|The sender account type|
|senderAddress1|string|none|The sender address 1|
|senderAmount|number(decimal)|none|The sender amount|
|senderBankName|string|none|The sender bank name|
|senderBankState|string|none|The sender bank State|
|senderDiscretionaryData|string|none|The sender discretionary data|
|senderEmail|string(email)|none|The sender email|
|senderId|string|none|The sender unique identifier exist in the system|
|senderIdType|string|none|The sender identifier type|
|senderName|string|none|The sender’s name|
|senderRoutingNumber|string|none|The sender routing number|
|senderState|string|none|The sender state|
|senderType|string|none|Type of the Sender for e.g., Corporate or Consumer|
|senderZip|string|none|The sender zipcode|
|ultimateSenderName|string|none|The ultimate sender’s name|
|ultimateSenderAccountNumber|string|none|The ultimate sender account number|
|ultimateSenderAddress1|string|none|The ultimate sender address 1|
|ultimateSenderAddress2|string|none|The ultimate sender address 2|
|ultimateSenderTaxId|string|none|The ultimate receiver tax number|
|ultimateSenderCity|string|none|The ultimate sender city|
|ultimateSenderState|string|none|The ultimate sender sate|
|ultimateSenderZip|string|none|The ultimate sender zipcode|
|ultimateSenderCountry|string|none|The ultimate sender country|
|bulkFileNumber|integer|none|Bulk file number|
|entryType|string|none|Whether the payment is Credit or Debit|
|paymentReturnDetails|Object|This will be populated when the payment is returned |Payment returns details.|
|paymentReturnDetails: code|string|none|Return code associated with the payment|
|paymentReturnDetails: description|string|none|Return code description|
|creationDateTime|string(date-time)|none|Date and Time payment is created|
|lastUpdatedTime|string(date-time)|none|The date and Time of payment got updated last|