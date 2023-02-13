---
title: Payments
---
 
## **Payments**

We believe in taking the complexity out of payments. By providing one single API for instant, domestic and international payments, you can access multiple rails like ACH, Fedwire, RTP and FedNow using Finzly Connect. Our payment engine powers this API, smartly routing it through the appropriate rail, based on rule-based workflows. 

Using the APIs, users can originate payments, request and process collection through US Fedwire, US ACH, RTP, FedNow and SWIFT. Several use cases can be brought to life through the application of these APIs in customer-facing apps. They can also be used to automate internal payment processes like invoice payments. The payment status APIs help in providing full transparency of the payments throughout the lifecycle of the payments.

<!-- ## **Payment Network** -->
![image info](./images/payment-network.png)

<br/><br/>

Benefits of Finzly Connect Payments API:
- Payments are optimized based on acceptance, speed of delivery and/or cost
- Event-driven notifications when payment statuses change, helping you offer exceptional CX
- Accepts payment instructions in different formats - ISO20022, SWIFT MT, custom and NACHA formats
- Reduced payment failures due to in-built smart routing capabilities
- Ability to repair exceptions
- Fallback options for alternative rails if payee bank is not on RTP/FedNow
- Ability to test payment flows before going live on our sandbox environment

**Payment capabilities**

The API offers various payment capabilities including but not limited to:
- Initiate payments
- Receive payments
- Receive payment statuses for ongoing payment transactions
- Request for payment refunds  
- Returns and cancellations 
- Retrieve payment information about payment transactions

<!-- Finzly connect APIs are designed with the mindset that it should be simple to understand and easy to
integrate. Hence, we have exposed one API to initiate a payment for multiple rails such as ACH, WIRE,
RTP, FedNow, etc.
The payment API is powered by the payment routing engine (rule-based workflow) to make it simple to
understand. The consumer does not have to choose or decide the payment rail or network (such as ACH,
RTP FedNow, etc.) to create a payment instead they have to choose from the simple options based on the
payment speed and cost, for instance, "Economy" for less cost and 2 to 3 business days to transfer the
money or "Instant” for little higher cost and instant money transfer. -->

<!-- ## **Features and Benefits** -->
<!-- <svg width="12" height="12" x="0" y="0" viewBox="0 0 32 32"> <g transform="matrix(-1,-1.2246467991473532e-16,1.2246467991473532e-16,-1,32,32)"><path d="M16 1a15 15 0 1 0 15 15A15.017 15.017 0 0 0 16 1zm2.707 20.293a1 1 0 1 1-1.414 1.414l-6-6a1 1 0 0 1 0-1.414l6-6a1 1 0 0 1 1.414 1.414L13.414 16z" fill="#003c90" data-original="#000000" class=""></path></g></svg> API supports both domestic as well as international payments using One API

<svg width="12" height="12" x="0" y="0" viewBox="0 0 32 32"> <g transform="matrix(-1,-1.2246467991473532e-16,1.2246467991473532e-16,-1,32,32)"><path d="M16 1a15 15 0 1 0 15 15A15.017 15.017 0 0 0 16 1zm2.707 20.293a1 1 0 1 1-1.414 1.414l-6-6a1 1 0 0 1 0-1.414l6-6a1 1 0 0 1 1.414 1.414L13.414 16z" fill="#003c90" data-original="#000000" class=""></path></g></svg> Payment Scheduling - It allows user to schedule a payment to the future date

<svg width="12" height="12" x="0" y="0" viewBox="0 0 32 32"> <g transform="matrix(-1,-1.2246467991473532e-16,1.2246467991473532e-16,-1,32,32)"><path d="M16 1a15 15 0 1 0 15 15A15.017 15.017 0 0 0 16 1zm2.707 20.293a1 1 0 1 1-1.414 1.414l-6-6a1 1 0 0 1 0-1.414l6-6a1 1 0 0 1 1.414 1.414L13.414 16z" fill="#003c90" data-original="#000000" class=""></path></g></svg> Repetitive Payments - It provides various options to set the repetitive payments such as Daily,
Weekly, Bi-Weekly, Monthly etc.  -->
<!-- ![image info](./images/payment-hub.png) -->

<!-- <br/><br/>
To initiate a payment, the developer must provide very minimal details as follows:

<svg width="12" height="12" x="0" y="0" viewBox="0 0 32 32"> <g transform="matrix(-1,-1.2246467991473532e-16,1.2246467991473532e-16,-1,32,32)"><path d="M16 1a15 15 0 1 0 15 15A15.017 15.017 0 0 0 16 1zm2.707 20.293a1 1 0 1 1-1.414 1.414l-6-6a1 1 0 0 1 0-1.414l6-6a1 1 0 0 1 1.414 1.414L13.414 16z" fill="#003c90" data-original="#000000" class=""></path></g></svg> Sender Account

&nbsp;&nbsp; 1. Sender Unique ID

<svg width="12" height="12" x="0" y="0" viewBox="0 0 32 32"> <g transform="matrix(-1,-1.2246467991473532e-16,1.2246467991473532e-16,-1,32,32)"><path d="M16 1a15 15 0 1 0 15 15A15.017 15.017 0 0 0 16 1zm2.707 20.293a1 1 0 1 1-1.414 1.414l-6-6a1 1 0 0 1 0-1.414l6-6a1 1 0 0 1 1.414 1.414L13.414 16z" fill="#003c90" data-original="#000000" class=""></path></g></svg> Receiver Information

&nbsp;&nbsp; 1. Receiver Unique 

<svg width="12" height="12" x="0" y="0" viewBox="0 0 32 32"> <g transform="matrix(-1,-1.2246467991473532e-16,1.2246467991473532e-16,-1,32,32)"><path d="M16 1a15 15 0 1 0 15 15A15.017 15.017 0 0 0 16 1zm2.707 20.293a1 1 0 1 1-1.414 1.414l-6-6a1 1 0 0 1 0-1.414l6-6a1 1 0 0 1 1.414 1.414L13.414 16z" fill="#003c90" data-original="#000000" class=""></path></g></svg> Amount

<svg width="12" height="12" x="0" y="0" viewBox="0 0 32 32"> <g transform="matrix(-1,-1.2246467991473532e-16,1.2246467991473532e-16,-1,32,32)"><path d="M16 1a15 15 0 1 0 15 15A15.017 15.017 0 0 0 16 1zm2.707 20.293a1 1 0 1 1-1.414 1.414l-6-6a1 1 0 0 1 0-1.414l6-6a1 1 0 0 1 1.414 1.414L13.414 16z" fill="#003c90" data-original="#000000" class=""></path></g></svg> Currency

<svg width="12" height="12" x="0" y="0" viewBox="0 0 32 32"> <g transform="matrix(-1,-1.2246467991473532e-16,1.2246467991473532e-16,-1,32,32)"><path d="M16 1a15 15 0 1 0 15 15A15.017 15.017 0 0 0 16 1zm2.707 20.293a1 1 0 1 1-1.414 1.414l-6-6a1 1 0 0 1 0-1.414l6-6a1 1 0 0 1 1.414 1.414L13.414 16z" fill="#003c90" data-original="#000000" class=""></path></g></svg> Speed – Economy or Economy Plus or Express or Instant

<svg width="12" height="12" x="0" y="0" viewBox="0 0 32 32"> <g transform="matrix(-1,-1.2246467991473532e-16,1.2246467991473532e-16,-1,32,32)"><path d="M16 1a15 15 0 1 0 15 15A15.017 15.017 0 0 0 16 1zm2.707 20.293a1 1 0 1 1-1.414 1.414l-6-6a1 1 0 0 1 0-1.414l6-6a1 1 0 0 1 1.414 1.414L13.414 16z" fill="#003c90" data-original="#000000" class=""></path></g></svg> Notes – Payment Notes

Based on the speed, Finzly’s payment hub would process the payment using the most cost-efficient
payment option available. The following lines of code would initiate a payment request successfully

```yaml Before
{
curl -X POST [URL]
-H "Content-Type: application/json"
-H "Authorization: bearer [ACCESS TOKEN]"
-d '{"externalReferenceId": "refid-128976","paymentCurrency": "USD","paymentAmount":
100.00,"speed": "Economy","paymentNotes": "Payment for the invoice #123","sender":
{"accountUID": "123452334"},"receiver": {"accountUID": "12334989"}}'
}

```
Developers can receive real-time webhook notifications for:

<svg width="12" height="12" x="0" y="0" viewBox="0 0 32 32"> <g transform="matrix(-1,-1.2246467991473532e-16,1.2246467991473532e-16,-1,32,32)"><path d="M16 1a15 15 0 1 0 15 15A15.017 15.017 0 0 0 16 1zm2.707 20.293a1 1 0 1 1-1.414 1.414l-6-6a1 1 0 0 1 0-1.414l6-6a1 1 0 0 1 1.414 1.414L13.414 16z" fill="#003c90" data-original="#000000" class=""></path></g></svg> Outgoing credit payment statuses

<svg width="12" height="12" x="0" y="0" viewBox="0 0 32 32"> <g transform="matrix(-1,-1.2246467991473532e-16,1.2246467991473532e-16,-1,32,32)"><path d="M16 1a15 15 0 1 0 15 15A15.017 15.017 0 0 0 16 1zm2.707 20.293a1 1 0 1 1-1.414 1.414l-6-6a1 1 0 0 1 0-1.414l6-6a1 1 0 0 1 1.414 1.414L13.414 16z" fill="#003c90" data-original="#000000" class=""></path></g></svg> Outgoing debit payment statuses

<svg width="12" height="12" x="0" y="0" viewBox="0 0 32 32"> <g transform="matrix(-1,-1.2246467991473532e-16,1.2246467991473532e-16,-1,32,32)"><path d="M16 1a15 15 0 1 0 15 15A15.017 15.017 0 0 0 16 1zm2.707 20.293a1 1 0 1 1-1.414 1.414l-6-6a1 1 0 0 1 0-1.414l6-6a1 1 0 0 1 1.414 1.414L13.414 16z" fill="#003c90" data-original="#000000" class=""></path></g></svg> Incoming 

<svg width="12" height="12" x="0" y="0" viewBox="0 0 32 32"> <g transform="matrix(-1,-1.2246467991473532e-16,1.2246467991473532e-16,-1,32,32)"><path d="M16 1a15 15 0 1 0 15 15A15.017 15.017 0 0 0 16 1zm2.707 20.293a1 1 0 1 1-1.414 1.414l-6-6a1 1 0 0 1 0-1.414l6-6a1 1 0 0 1 1.414 1.414L13.414 16z" fill="#003c90" data-original="#000000" class=""></path></g></svg> Incoming drawdowns

<svg width="12" height="12" x="0" y="0" viewBox="0 0 32 32"> <g transform="matrix(-1,-1.2246467991473532e-16,1.2246467991473532e-16,-1,32,32)"><path d="M16 1a15 15 0 1 0 15 15A15.017 15.017 0 0 0 16 1zm2.707 20.293a1 1 0 1 1-1.414 1.414l-6-6a1 1 0 0 1 0-1.414l6-6a1 1 0 0 1 1.414 1.414L13.414 16z" fill="#003c90" data-original="#000000" class=""></path></g></svg> Incoming debit requests

<svg width="12" height="12" x="0" y="0" viewBox="0 0 32 32"> <g transform="matrix(-1,-1.2246467991473532e-16,1.2246467991473532e-16,-1,32,32)"><path d="M16 1a15 15 0 1 0 15 15A15.017 15.017 0 0 0 16 1zm2.707 20.293a1 1 0 1 1-1.414 1.414l-6-6a1 1 0 0 1 0-1.414l6-6a1 1 0 0 1 1.414 1.414L13.414 16z" fill="#003c90" data-original="#000000" class=""></path></g></svg> Incoming returns

<svg width="12" height="12" x="0" y="0" viewBox="0 0 32 32"> <g transform="matrix(-1,-1.2246467991473532e-16,1.2246467991473532e-16,-1,32,32)"><path d="M16 1a15 15 0 1 0 15 15A15.017 15.017 0 0 0 16 1zm2.707 20.293a1 1 0 1 1-1.414 1.414l-6-6a1 1 0 0 1 0-1.414l6-6a1 1 0 0 1 1.414 1.414L13.414 16z" fill="#003c90" data-original="#000000" class=""></path></g></svg> Incoming NOCs

<svg width="12" height="12" x="0" y="0" viewBox="0 0 32 32"> <g transform="matrix(-1,-1.2246467991473532e-16,1.2246467991473532e-16,-1,32,32)"><path d="M16 1a15 15 0 1 0 15 15A15.017 15.017 0 0 0 16 1zm2.707 20.293a1 1 0 1 1-1.414 1.414l-6-6a1 1 0 0 1 0-1.414l6-6a1 1 0 0 1 1.414 1.414L13.414 16z" fill="#003c90" data-original="#000000" class=""></path></g></svg> Incoming RFPs -->