---
title: Finzly Connect API Changelog
---



## **Changelog** 


### **July 7th,2023**

|**Change**|**Category**|**Description**|
| :- | :- | :- | 
| Payment Credit API | Enhancement | Following updates happened to the existing payment API [/v3/payments/creditrequest] <br><br> <ul><li>Added "correspondentBankId" in the payment request to allow user to provide correspondent bank routing number for international Fedwire payment request [Where, The receiver bank country is outside of the USA ].</li></ul><ul><li>Added "costCenter" to the additionalInfo to assign valid cost center by the user</li></ul> |
| Webhook API | Enhancement | Added following payment attributes to the existing webhook payload <br><br> <ul><li>networkRefId, otherBankRefId</li></ul><ul><li> senderIdType2, senderId2</li></ul><ul><li>	senderBankIdType, senderBankId, senderAddress2, senderCity, senderCountry, senderBankAddress1, senderBankAddress2, senderBankCity, senderBankZip</li></ul><ul><li>receiverAddress2, receiverCity, receiverCountry, receiverBankIdType, receiverBankId, receiverBankAddress1, receiverBankAddress2, receiverBankCity, receiverBankZip, receiverBankCountry</li></ul><ul><li>intermediarySenderBankIdType, intermediarySenderBankId, intermediarySenderBankName, intermediarySenderBankAddress1, intermediarySenderBankAddress2, intermediarySenderBankCity, intermediarySenderBankState,intermediarySenderBankZip,intermediarySenderBankCountry</li></ul><ul><li>intermediaryReceiverBankIdType, intermediaryReceiverBankId, intermediaryReceiverBankName, intermediaryReceiverBankAddress1, intermediaryReceiverBankAddress2, intermediaryReceiverBankCity, intermediaryReceiverBankState, intermediaryReceiverBankZip, intermediaryReceiverBankCountry</li></ul><ul><li>originatorToBeneficiaryInformation, FiToFiInformation, senderToRecieverInfo, referenceForBeneficiary, beneficiaryFIAdviceCode, beneficiaryFIAdviceInformation, beneficiaryAdviceCode, beneficiaryAdviceInformation, beneficiaryFIInformation, requestMethod</li></ul><ul><li>achSecCode, achTransactionCode, achTraceId, achBatchId</li></ul><ul><li>fedwireBusinessFunctionCode, fedwireDetailsOfCharge, fedwireComments	</li></ul>|
| Payment Documentation | Enhancement | Enhanced Payment APIs documentation with an addtional details on the payment attributes definition and limits |


### **April 14th,2023**

|**Change**|**Category**|**Description**|
| :- | :- | :- | 
| Payment API | Enhancement | Following updates happened to the existing payment APIs [/v3/payments/creditrequest] and [/v3/payments/debitrequest] <ul><li>The externalReferenceId in the payment request will be set to the payment transaction as “sourceReferenceId”.</li></ul><ul><li> The bankIdType in the sender or debtor request will have either [NID or SWIFT] instead of [NID or BIC]</li></ul><ul><li> The “accountCurrency” added to the receiver object this is needed for the international payments where user is making a FX transaction to buy the foreign currency.</li></ul><ul><li> The possible values for the “bankIdType” are changed from [By NID, BY ADDRESS, BY SWIFT] to [NID, SWIFT, ADDRESS]. This change is applicable to the all [Bank] object used in payment request object.</li></ul> |
| Payment API | Enhancement | Added 'feeName' to the Fee object. This is an optional attribute allow user to assign the custom name to the fee. |
| Payment API | Enhancement | Added additional attributes to the Get Payment API response [/v3/payments/{paymentUID}] such as <ul><li>Intermediary details for the Sender and Receiver</li></ul> <ul><li>Sender and Receiver additional details on the address and bank</li></ul>|
| Payment Webhook API | Enhancement | Added 'externalReferenceId' to the payment webhook response |
| Positive Rules APIs | Enhancement | Positive Rules Finzly FX APIs enables third parties, banks, and bank's downstream partners to create ,manage rules for ACH Positive Pay and Fedwire Drawdowns. Its also helps in accepting or rejecting any exceptions reported.With this APIs you can now <ul><li>Create new rules or edit existing rules</li><li> Temporarily suspend or activate a rules. Delete a rules if its not longer valid</li><li>Manage exceptions by approving or rejecting.Approve all is an additional feature to ease the operations</li></ul> |
| Payment API | Enhancement | Updated existing create payment APIs to allow user to provide the sender routing number in a scenario where the bank account is not configured  in the CRM application |
| Customer API | Enhancement | Added additional attributes to the customer account APIs for the create, get and update operations <ul><li>Callback- Yes or No</li><li>Callback Limit - Amount</li><li>Cost Center</li></ul>  |
| FX API | Enhancement| The following changes are performed to the existing FX APIs <ul><li>Added two additional attributes to the "/v2/fx/accept" API <ul> <li>autoCover - Yes or No </li><li>autoCoverDelay - Number in minutes</li></ul></li><li>Added a new API to perform cover trade "/v2/fx/forexContractNo}/cover"<ul><li>Require a FX Contract Number</li></ul></li></ul> |




### **November 18th,2022**

|**Change**|**Category**|**Description**|
| :- | :- | :- | 
| Foreign Exchange APIs | Enhancement | Foreign Exchange Finzly FX APIs enables third-parties,banks, and bank's downstream partners to initiate and Manage FX trades for their customers. With this API, you can now:- <ul><li>Get FX Quote: Ability to get the realtime FX rate.</li><li>Accept/Reject FX Quote: Allow user to either accept or reject the quote.</li><li>Get trade by ForexContractNo:Retrieve trade details based on the FX contract number.</li><li>Delete Trade by ForexContractNo: Allow user to cancel the trade.</li></ul> |
| UserAdmin APIs - User & Roles | Enhancement | User and Roles API allows bank, Bank's 3rd party system or Fintech to define roles to control the user access and manage user to allow them to access the system.<br> With this API, you can now:<br> <ul><li>Application <ul><li>Get/Search Application details</li></ul></li><li>Admin - user <ul><li>Create/Update/Delete user</li><li>Get Users</li><li>Get User by UID</li><li>Activate/Suspend User</li></ul></li><li>Admin - Role<ul><li>Create/Update/Delete user</li><li>Get Role By UID</li><li>Search Role</li></ul></li></ul>  |
| Payment APIs - Additional capability to the Payment APIs | Enhancement | Enhanced the following payment APIs<br> <ul><li>API:/v3/payments/creditrequest:<ul><li>Added "intermediaryBank" to the "receiver" object</li><li>Added "fxContractNumber" to the "additionalInfo"</li><li>Added "regulatoryReporting" to the "additionalInfo"</li></ul></li><li>API:/v3/payments/debitrequest:<ul><li>Added "intermediaryBank" to the "creditor" object</li></ul></li></ul> |

