---
title: Finzly API Overview Section  
---

## **Overview**

Finzly Connect is the universal payment API for the developers to access all the payment rails, without
having to worry about the network and messaging rules. Finzly Connects offers REST API and webhook
notifications to access any Finzly powered bank. Finzly has normalized the payment data and has made
the payment processing super simple, so a bank customer, whether it is a fintech, business or an
individual, doesn’t have to worry about the messaging rules. A developer can access ACH, Domestic
Wires, International Wires, RTP and FedNow using Finzly Connect, and connect to their favorite Finzly
Bank.

## **Payment Network**
![image info](./images/payment-network.png)

<br/><br/>
Finzly connect APIs are designed with the mindset that it should be simple to understand and easy to
integrate. Hence, we have exposed one API to initiate a payment for multiple rails such as ACH, WIRE,
RTP, FedNow, etc.
The payment API is powered by the payment routing engine (rule-based workflow) to make it simple to
understand. The consumer does not have to choose or decide the payment rail or network (such as ACH,
RTP FedNow, etc.) to create a payment instead they have to choose from the simple options based on the
payment speed and cost, for instance, "Economy" for less cost and 2 to 3 business days to transfer the
money or "Instant” for little higher cost and instant money transfer.

## **Features and Benefits**
<svg width="12" height="12" x="0" y="0" viewBox="0 0 32 32"> <g transform="matrix(-1,-1.2246467991473532e-16,1.2246467991473532e-16,-1,32,32)"><path d="M16 1a15 15 0 1 0 15 15A15.017 15.017 0 0 0 16 1zm2.707 20.293a1 1 0 1 1-1.414 1.414l-6-6a1 1 0 0 1 0-1.414l6-6a1 1 0 0 1 1.414 1.414L13.414 16z" fill="#003c90" data-original="#000000" class=""></path></g></svg> API supports both domestic as well as international payments using One API

<svg width="12" height="12" x="0" y="0" viewBox="0 0 32 32"> <g transform="matrix(-1,-1.2246467991473532e-16,1.2246467991473532e-16,-1,32,32)"><path d="M16 1a15 15 0 1 0 15 15A15.017 15.017 0 0 0 16 1zm2.707 20.293a1 1 0 1 1-1.414 1.414l-6-6a1 1 0 0 1 0-1.414l6-6a1 1 0 0 1 1.414 1.414L13.414 16z" fill="#003c90" data-original="#000000" class=""></path></g></svg> Payment Scheduling - It allows user to schedule a payment to the future date

<svg width="12" height="12" x="0" y="0" viewBox="0 0 32 32"> <g transform="matrix(-1,-1.2246467991473532e-16,1.2246467991473532e-16,-1,32,32)"><path d="M16 1a15 15 0 1 0 15 15A15.017 15.017 0 0 0 16 1zm2.707 20.293a1 1 0 1 1-1.414 1.414l-6-6a1 1 0 0 1 0-1.414l6-6a1 1 0 0 1 1.414 1.414L13.414 16z" fill="#003c90" data-original="#000000" class=""></path></g></svg> Repetitive Payments - It provides various options to set the repetitive payments such as Daily,
Weekly, Bi-Weekly, Monthly etc. 

![image info](./images/payment-hub.png)

<br/><br/>
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

<svg width="12" height="12" x="0" y="0" viewBox="0 0 32 32"> <g transform="matrix(-1,-1.2246467991473532e-16,1.2246467991473532e-16,-1,32,32)"><path d="M16 1a15 15 0 1 0 15 15A15.017 15.017 0 0 0 16 1zm2.707 20.293a1 1 0 1 1-1.414 1.414l-6-6a1 1 0 0 1 0-1.414l6-6a1 1 0 0 1 1.414 1.414L13.414 16z" fill="#003c90" data-original="#000000" class=""></path></g></svg> Incoming RFPs