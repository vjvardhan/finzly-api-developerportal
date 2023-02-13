---
title: Accept FX Quote
---

### **Accept FX Quote** 
[PUT /fx/accept](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/acceptFXQuoteV2/)

**HTTP Method: PUT**

**Description -** Sending PUT request to **/fx/accept** endpoint allows users to accept FX Quote using quoteUUID in the API request path. All the request parameters and objects are specified below - 

**Request Parameters**


|**Name** |**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|body|body|[FXAcceptQuoteRequest](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/acceptFXQuoteV2/)|false|none|

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
|data|<p>[FXAcceptQuoteResponse_data](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/reference/operation/acceptFXQuoteV2/)</p><p></p>|false|none|none|

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