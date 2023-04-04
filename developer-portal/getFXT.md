---
title: Get FX Trade
---

### **Get FX trade information (v2)**

[GET /fx/{forexContractNo}](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/fxapi/operation/getFXTradeInformationV2/)

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
|data|<p>[FXTradeInfoResponse_data](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/fxapi/operation/getFXTradeInformationV2/)</p><p></p>|false|none|none|

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