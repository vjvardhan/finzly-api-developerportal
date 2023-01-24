---
title: Finzly API Errors
---

### **Errors** 
**Http Response Codes**

|Code|Reason|
| :- | :- |
|200 - OK|Successfully processed the request|
|201 - Created|The object was successfully created|
|204 - No Content|No Content, Successfully processed the request|
|400 - Bad Request|The request was rejected, most likely due to invalid parameters|
|401 & 403 |Unauthorized or forbidden request|
|404 - Not Found|The resource does not exist|
|409 - Conflict|This typically occurs when duplicate requests are received even while the original request is being processed.|
|422 - Unprocessable Entity|The request body contains well-formed (i.e., syntactically correct), but semantically erroneous, instructions.|
|500 - Internal Server Error|Something went wrong with Digital Disbursements and the request could not be processed.|


**400 Bad Request**

The 400 (Bad Request) status code indicates that the server cannot or will not process the request due to something that is perceived to be a client error (e.g., malformed request syntax, invalid request message framing, or deceptive request routing).

**402 Payment Required**

The 402 (Payment Required) status code is reserved for future use.

**403 Forbidden**

The 403 (Forbidden) status code indicates that the server understood the request but refuses to authorize it. A server intending to make the reason for the forbidden request public can describe it in the response payload (if any).

If authentication credentials were provided in the request, the server considers them insufficient to grant access. The client SHOULD NOT automatically repeat the request with the same credentials. The client MAY repeat the request with new or different credentials. However, a request might be forbidden for reasons unrelated to the credentials.

An origin server that wishes to "hide" the current existence of a forbidden target resource MAY instead respond with a status code of 404 (Not Found).

**404 Not Found**

The 404 (Not Found) status code indicates that the origin server did not find a current representation for the target resource or is not willing to disclose that one exists. A 404 status code does not indicate whether this lack of representation is temporary or permanent; the 410 (Gone) status code is preferred over 404 if the origin server knows, presumably through some configurable means, that the condition is likely to be permanent.

A 404 response is cacheable by default, i.e., unless otherwise indicated by the method definition or explicit cache controls (see [Section 4.2.2 of \[RFC7234\]](https://www.rfc-editor.org/rfc/rfc7234#section-4.2.2)).

**405 Method Not Allowed**

The 405 (Method Not Allowed) status code indicates that the method received in the request line is known by the origin server but not supported by the target resource. The origin server MUST generate an Allow header field in a 405 response containing a list of the target resource's currently supported methods.

A 405 response is cacheable by default, i.e., unless otherwise indicated by the method definition or explicit cache controls

**406 Not Acceptable**

The 406 (Not Acceptable) status code indicates that the target resource does not have a current representation that would be acceptable to the user agent, according to the proactive negotiation header fields received in the request and the server is unwilling to supply a default representation.

The server SHOULD generate a payload containing a list of available representation characteristics and corresponding resource identifiers from which the user or user agent can choose the most  appropriate. A user agent MAY automatically select the most suitable choice from that list. 
