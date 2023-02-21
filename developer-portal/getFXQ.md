---
title: Get FX Quote
---

### **Get FX Quote**
[POST /fx/quote](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/paymentapi/operation/getFXQuoteV2/)

**HTTP Method: GET**

**Description -** Sending a GET request to the **/fx/quote** endpoint allows users to request a quote for FX trade. All the parameters and objects are specified below - 

**Request Parameters**


|**Name** |**In**|**Type**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|body|body|[FXQuoteRequest](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/paymentapi/operation/getFXQuoteV2/)|true|Quote request attributes to get the quote for a given ccy pair|

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
|data|<p>[FXQuoteResponse_data](https://finzlyconnect-api-developer-portal.redoc.ly/openapi/paymentapi/operation/getFXQuoteV2/)</p><p></p>|false|none|none|