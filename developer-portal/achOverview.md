---
title: ACH Overview 
---



## **ACH** 

ACH (Automated Clearing House) is the most popular, and highly used payment network that was first launched in [xxxx]. ACH payments are exchanged in NACHA formatted files. NACHA sets the rules and guidelines for the processing of ACH payments. After the power of RESTful APIs were proved to be critical for a connected e-commerce and treasury, the need to offer ACH payments via REST API has become critical for the success of banks. 

**ACH Terminologies** 

While ACH payments are cheaper compared to other payment networks, they have most the complexity than other payment rails, as ACH has evolved over several decades to support various use cases of the industry.

**Files & Batches**

Each payment is created as a payment entry, and the entries are grouped in batches and the batches are grouped in a file. Each file and batch may be balanced or unbalanced. 

**Balanced & Unbalanced Files**

In a balanced file, the outbound debits and credits are offset with a customer’s DDA account entry. In an unbalanced file, the bank would offset it with the customer’s default account. 


