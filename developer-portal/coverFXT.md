---
title: Cover FX Trade
---

### **Cover FX Trade**
[GET /fx/{forexContractNo}/cover](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/paymentapi/operation/coverFXTradeV2/)

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
|data|<p>[FXCoverTradeResponse_data](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/paymentapi/operation/coverFXTradeV2/)</p><p></p>|false|none|none|

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