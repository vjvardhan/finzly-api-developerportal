---
title: Foreign Exchange
---


## **Foreign Exchange**

Foreign Exchange (forex or FX) is trading one currency for another. For example, one can swap the U.S. dollar for the euro. Foreign Exchange Finzly FX APIs enable third parties, banks, and banks' downstream partners to initiate and manage FX trades for their customers.

Following functions helps you to understand the current FX capabilities exposed via APIs

1. FX Quote
2. FX Quote Accept/Reject
3. Get Trade By ForexContractNo
4. Delete Trade By ForexContractNo

## **API Functions**
### **Get FX Quote**
[POST /fx/quote](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/getFXQuote/)

**HTTP Method: GET**

**Description -** Sending a GET request to the **/fx/quote** endpoint allows users to request a quote for FX trade. All the parameters and objects are specified below - 

**Request Parameters**


|**Name** |**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|body|body|[FXQuoteRequest](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/getFXQuote/)|true|Quote request attributes to get the quote for a given ccy pair|

**JSON Response**

A successful POST request to this endpoint returns the following data-

**Response Code - 200**

```yaml Before
{
  "status": "Success or Failure",
  "code": "FXQUOTE001 etc.",
  "message": "Failed to get a FX Quote due to the mandatory attribute  is not provide.",
  "data": {
    "externalReferenceId": "REQ123 or 1274878",
    "quoteUUID": "123e4567-e89b-12d3-a456-426614174000",
    "expirySeconds": 30,
    "exchangeRate": 1.2,
    "invertedRate": 0.83,
    "sellCurrency": "EUR",
    "buyCurrency": "INR",
    "fundingAmount": 10000,
    "transferAmount": 1000,
    "productType": "SPOT or FORWARD",
    "tenor": "SPOT, ON, TN, nW, nM, nY where n is a number",
    "valueDate": "2020-01-01",
    "externalPricingSystemRefId": "R1274878 etc."
  }
}

```

|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|status|string|false|none|This will return Success/Failed|
|code|string|false|none|This will indicate the error code in case of API error|
|message|string|false|none|This will be the detailed error message indicating what failed and how to fix the issue|
|data|<p>[FXQuoteResponse_data](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/getFXQuote/)</p><p></p>|false|none|none|

### **Accept FX Quote** 
[PUT /fx/accept](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/acceptFXQuote/)

**HTTP Method: PUT**

**Description -** Sending PUT request to **/fx/accept** endpoint allows users to accept FX Quote using quoteUUID in the API request path. All the request parameters and objects are specified below - 

**Request Parameters**


|**Name** |**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|body|body|[FXAcceptQuoteRequest](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/acceptFXQuote/)|false|none|

**JSON Response**

A successful GET request to this endpoint returns the following data-

**Response Code - 200**

```yaml Before
{
  "status": "Success or Failure",
  "code": "FXQUOTE002 etc.",
  "message": "Failed to accept a quote: ",
  "data": {
    "quoteUUID": "123e4567-e89b-12d3-a456-426614174000",
    "forexContractNo": "123898",
    "tradeStatus": "Booked etc.",
    "tradeDate": "2020-01-01",
    "ccyPair": "USDEUR",
    "direction": "Buy or Sell",
    "baseCcy": "USD",
    "baseAmount": 1000,
    "quoteCcy": "USD",
    "quoteAmount": 900,
    "tenor": "SPOT, ON, TN, nW, nM, nY where n is a number",
    "exchangeRate": 1.2,
    "valueDate": "2020-01-01",
    "referenceSpotRate": 100,
    "referenceFwdPoints": 100,
    "executionTime": "2019-08-24",
    "externalPricingSystemRefId": "R1274878 etc."
  }
}

```
|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|status|string|false|none|This will return Success/Failed|
|code|string|false|none|This will indicate the error code in case of API error|
|message|string|false|none|This will be the detailed error message indicating what failed and how to fix the issue|
|data|<p>[FXAcceptQuoteResponse_data](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/acceptFXQuote/)</p><p></p>|false|none|none|

**FX Accept Quote Response Data**


|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|quoteUUID|string|false|none|FX Quote universally unique identifier (UUID)|
|forexContractNo|string|false|none|FX contract number assigned by the system after acceptance.|
|tradeStatus|string|false|none|Trade status after acceptance of fx quote|
|tradeDate|string(date)|false|none|The trade date is the date on which a transaction was executed. The date format is in yyyy-mm-dd.|
|ccyPair|string|false|none|A currency pair is the quotation of two different currencies, with the value of one currency being quoted against the other|
|direction|string|false|none|Buy or Sell|
|baseCcy|string|false|none|The base currency is the first currency stated in a currency pair quote|
|baseAmount|number|false|none|Base currency amount|
|quoteCcy|string|false|none|The second currency is the quote currency, which states how much of the quote currency is required to buy one unit of the base currency.|
|quoteAmount|number|false|none|Quote currency amount|
|tenor|string|false|none|The length of time remaining before a financial contract expires. Only one is needed between tenor or valueDate.|
|exchangeRate|number|false|none|The price of one currency in terms of the other|
|valueDate|string(date)|false|none|The delivery date on which counterparties to a transaction agree to settle their respective obligations by making payments and transferring ownership.Only one is needed between tenor or valueDate. The date format is in yyyy-mm-dd.|
|referenceSpotRate|number|false|none|the offered rate|
|referenceFwdPoints|number|false|none|The number of basis points added to or subtracted from the current spot rate of a currency pair to determine the forward rate for delivery on a specific value date|
|executionTime|string(date)|false|none|The execution time|
|externalPricingSystemRefId|string|false|none|Unique reference id returned by the external system provider.|

### **Reject FX Quote**
[PUT /fx/{quoteUUID}/reject](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/rejectFXQuote/)

**HTTP Method: PUT**

**Description -** Sending a PUT request to **PUT /fx/{quoteUUID}/reject** endpoint allows user to reject FX Quote using quoteUUID in the path of the API request. All the request parameters and objects are mentioned below - 

**Request Parameters**



|**Name** |**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|quoteUUID|path|string|true|none|


**JSON Response**

A successful PUT request to this endpoint returns the following data -

**Response Code - 200**
```yaml Before
{
  "status": "Success or Failure",
  "code": "FXQUOTE003 etc.",
  "message": "Failed to reject a quote: ",
  "data": {
    "quoteUUID": "123e4567-e89b-12d3-a456-426614174000",
    "fxQuoteStatus": "Rejected"
  }
}

```
|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|status|string|false|none|This will return Success/Failed|
|code|string|false|none|This will indicate the error code in case of API error|
|message|string|false|none|This will be the detailed error message indicating what failed and how to fix the issue|
|data|<p>[FXRejectQuoteResponse_data](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/rejectFXQuote/)</p><p></p>|false|none|none|

**FX Reject Quote Response Data**
```yaml Before
{
  "quoteUUID": "123e4567-e89b-12d3-a456-426614174000",
  "fxQuoteStatus": "Rejected"
}

```
|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|quoteUUID|string|false|none|FX Quote universally unique identifier (UUID)|
|fxQuoteStatus|string|false|none|FX Quote status after rejection|

### **Get FX trade information (v2)**

[GET /fx/{forexContractNo}](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/getFXTradeInformation/)

**HTTP Method: GET**

**Description -** Sending a GET request to  **/fx/{forexContractNo}** allows users to get FX trade information using forexContractNo in the path of the API request. All the request parameters and objects are mentioned below - 



**Request Parameters**


|**Name** |**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|forexContractNo|path|string|true|none|

**JSON Response**

A successful GET request to this endpoint returns the following data -

**Response Code - 200**

```yaml Before
{
  "status": "Success or Failure",
  "code": "FX001 etc.",
  "message": "Failed to get trade information: ",
  "data": {
    "forexContractNo": "123898",
    "tradeDate": "2020-01-01",
    "ccyPair": "USDEUR",
    "direction": "Buy or Sell",
    "baseCcy": "USD",
    "baseAmount": 1000,
    "quoteCcy": "USD",
    "quoteAmount": 900,
    "tenor": "SPOT, ON, TN, nW, nM, nY where n is a number",
    "exchangeRate": 1.2,
    "valueDate": "2020-01-01",
    "referenceSpotRate": 100,
    "referenceFwdPoints": 100,
    "executionTime": "2019-08-24"
  }
}

```

|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|status|string|false|none|This will return Success/Failed|
|code|string|false|none|This will indicate the error code in case of API error|
|message|string|false|none|This will be the detailed error message indicating what failed and how to fix the issue|
|data|<p>[FXTradeInfoResponse_data](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/getFXTradeInformation/)</p><p></p>|false|none|none|

**FX Trade Response Data**

```yaml Before
{
  "forexContractNo": "123898",
  "tradeDate": "2020-01-01",
  "ccyPair": "USDEUR",
  "direction": "Buy or Sell",
  "baseCcy": "USD",
  "baseAmount": 1000,
  "quoteCcy": "USD",
  "quoteAmount": 900,
  "tenor": "SPOT, ON, TN, nW, nM, nY where n is a number",
  "exchangeRate": 1.2,
  "valueDate": "2020-01-01",
  "referenceSpotRate": 100,
  "referenceFwdPoints": 100,
  "executionTime": "2019-08-24"
}

```

|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|forexContractNo|string|false|none|FX contract number assigned by the system for a given trade.|
|tradeDate|string(date)|false|none|The trade date is the date on which a transaction was executed. The date format is in yyyy-mm-dd.|
|ccyPair|string|false|none|A currency pair is the quotation of two different currencies, with the value of one currency being quoted against the other|
|direction|string|false|none|Buy or Sell|
|baseCcy|string|false|none|The base currency is the first currency stated in a currency pair quote|
|baseAmount|number|false|none|Base currency amount|
|quoteCcy|string|false|none|The second currency is the quote currency, which states how much of the quote currency is required to buy one unit of the base currency.|
|quoteAmount|number|false|none|Quote currency amount|
|tenor|string|false|none|The length of time remaining before a financial contract expires. Only one is needed between tenor or valueDate.|
|exchangeRate|number|false|none|The price of one currency in terms of the other|
|valueDate|string(date)|false|none|The delivery date on which counterparties to a transaction agree to settle their respective obligations by making payments and transferring ownership.Only one is needed between tenor or valueDate. The date format is in yyyy-mm-dd.|
|referenceSpotRate|number|false|none|The price of one currency in terms of the other|
|valueDate|string(date)|false|none|The delivery date on which counterparties to a transaction agree to settle their respective obligations by making payments and transferring ownership.Only one is needed between tenor or valueDate. The date format is in yyyy-mm-dd.|
|referenceSpotRate|number|false|none|the offered rate|
|referenceFwdPoints|number|false|none|The number of basis points added to or subtracted from the current spot rate of a currency pair to determine the forward rate for delivery on a specific value date|
|executionTime|string(date)|false|none|The execution time|

### **Cover FX Trade**
[GET /fx/{forexContractNo}/cover](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/coverFXTrade/)

**HTTP Method: GET**

**Description -** Sending a GET request to the **GET /fx/{forexContractNo}/cover** endpoint allows users to cover FX trade by passing the forexContractNo in the path of the API request. All the parameters and objects are specified below - 

**Request Parameters**


|**Name** |**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|forexContractNo|path|string|true|none|

**JASON Response**

A successful GET request to this endpoint returns the following data -

**Response Code - 200**
```yaml Before
{
  "status": "Success or Failure",
  "code": "FX001 etc.",
  "message": "Failed to perform the cover trade: ",
  "data": {
    "forexContractNo": "123898",
    "coverTradeNo": "990919",
    "externalPricingSystemRefId": "R1274878 etc.",
    "channel": "API",
    "customerIdType": "CustomerUID, CustomerShortName,CustomerId, DDA",
    "customerId": "112344 for DDA",
    "tradeDate": "2020-01-01",
    "valueDate": "2020-01-01",
    "ccyPair": "USDEUR",
    "direction": "Buy or Sell",
    "baseCcy": "USD",
    "baseAmount": 1000,
    "quoteCcy": "EUR",
    "quoteAmount": 955.08,
    "tenor": "SPOT, ON, TN, nW, nM, nY where n is a number",
    "allInRate": 0.98,
    "referenceSpotRate": 100
  }
}

```
|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|status|string|false|none|This will return Success/Failed|
|code|string|false|none|This will indicate the error code in case of API error|
|message|string|false|none|This will be the detailed error message indicating what failed and how to fix the issue|
|data|<p>[FXCoverTradeResponse_data](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/coverFXTrade/)</p><p></p>|false|none|none|

**FX Cover Trader Response Data**

```yaml Before
{
  "forexContractNo": "123898",
  "coverTradeNo": "990919",
  "externalPricingSystemRefId": "R1274878 etc.",
  "channel": "API",
  "customerIdType": "CustomerUID, CustomerShortName,CustomerId, DDA",
  "customerId": "112344 for DDA",
  "tradeDate": "2020-01-01",
  "valueDate": "2020-01-01",
  "ccyPair": "USDEUR",
  "direction": "Buy or Sell",
  "baseCcy": "USD",
  "baseAmount": 1000,
  "quoteCcy": "EUR",
  "quoteAmount": 955.08,
  "tenor": "SPOT, ON, TN, nW, nM, nY where n is a number",
  "allInRate": 0.98,
  "referenceSpotRate": 100
}



```



|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|forexContractNo|string|false|none|FX contract number assigned by the system for a given trade.|
|coverTradeNo|string|false|none|Unique cover trade number assigned by the system.Unique cover trade number assigned by the system.|
|externalPricingSystemRefId|string|false|none|Unique reference id provided by the external system|
|channel|string|false|none|Channel associated with the cover trade.|
|customerIdType|string|false|none|CustomerId type associated with the cover trade|
|customerId|string|false|none|The value based on the customerIdType associated with the cover trade|
|tradeDate|string|false|none|The trade date is the date on which a transaction was executed. The date format is in yyyy-mm-dd.|
|valueDate|number|false|none|The delivery date on which counterparties to a transaction agree to settle their respective obligations by making payments and transferring ownership.Only one is needed between tenor or valueDate. The date format is in yyyy-mm-dd.|
|ccyPair|string|false|none|A currency pair is the quotation of two different currencies, with the value of one currency being quoted against the other|
|direction|string|false|none|Buy or Sell|
|baseCcy|string|false|none|The base currency is the first currency stated in a currency pair quote|
|baseAmount|number|false|none|Base currency amount|
|quoteCcy|string|false|none|The second currency is the quote currency, which states how much of the quote currency is required to buy one unit of the base currency.|
|quoteAmount|number|false|none|Quote currency amount|
|tenor|string|false|none|The length of time remaining before a financial contract expires. Only one is needed between tenor or valueDate.|
|allInRate|number|false|none|The all in rate associated with the cover trade|
|referenceSpotRate|number|false|none|the offered rate|

### **Cancel FX Trade**
[DELETE /fx/{forexContractNo}/cancel](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/cancelFXTrade/)

**HTTP Method: Delete**

**Description -** Sending a DELETE request to the **/fx/{forexContractNo}/cancel** endpoint allows users to cancel FX trade by passing the forexContractNo in the path of the API request. All the parameters and objects are specified below - 

**Request Parameters**


|**Name** |**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|forexContractNo|path|string|true|none|

**JASON Response**

A successful Delete request to this endpoint returns the following data -

**Response Code - 200**

```yaml Before
{
  "status": "Success or Failure",
  "code": "FX001 etc.",
  "message": "Failed to cancel a trade: ",
  "data": {
    "forexContractNo": "123898",
    "tradeStatus": "Cancelled etc."
  }
}

```

|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|status|string|false|none|This will return Success/Failed|
|code|string|false|none|This will indicate the error code in case of API error|
|message|string|false|none|This will be the detailed error message indicating what failed and how to fix the issue|
|data|<p>[FXTradeCancelResponse_data](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/cancelFXTrade/)</p><p></p>|false|none|none|

**FX Trade Cancel Response Data**
```yaml Before
{
  "forexContractNo": "123898",
  "tradeStatus": "Cancelled etc."
}
```

|**Name**|**Type**|**Required**|**Restrictions**|**Description**|
| :- | :- | :- | :- | :- |
|forexContractNo|string|false|none|FX contract number assigned by the system for a given trade.|
|tradeStatus|string|false|none|Trade status after trade cancelation|

