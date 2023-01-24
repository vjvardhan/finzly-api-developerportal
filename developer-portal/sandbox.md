---
title: Sandbox and Testing
---




# **Getting started with Finzly APIs**



## **Authentication**
Our APIs use oAuth 2.0 authentication protocol to provide the secure access. You will use our API keys with grant type “Client Credentials” to fetch an access token. This token is digitally signed and contains access information such as user role mapping etc. Access token is a short-lived token (30 sec). To authenticate and authorize your API calls, you will have to pass the access token in authorization header with “bearer” prefix. 

![image info](./images/auth.png)


**Sample Request**
```yaml Before 

curl -X POST [URL] 
-H "Content-Type: application/x-www-form-urlencoded" 
-H 'Authorization: Basic [Base64(apikey:apisecert)]' 
-d 'grant_type=client_credentials'

```

**Sample Response**

```yaml Before 
{
 "access_token": "",
 "expires_in": 14400,
 "refresh_expires_in": 1800,
 "refresh_token":"",
 "token_type": "bearer",
}

```

Finzly Support creates your credentials, users in your team, and API Keys.
Using the API keys, you can access the Finzly API.
Now you can invoke the APIs to test the use cases. To commence your evaluation, you will require an evaluation and integration environment set up for you.

## **Sandbox and testing**
The sandbox environment is an environment you can play around with and use as a testbed for development. Customers must test their business flows in this environment before moving to the production environment. You must use test customers and test account numbers in the sandbox environment. Your business bank will onboard you into the sandbox environment and provide you with the API credentials.

After testing and validating the use cases to your satisfaction, you can sign off on evaluation.

Please contact the Finzly support team to validate the integration.


## **API Access**

Click [API Access](https://finzly.com/api-access) to fill in your contact information to get the sandbox API keys mailed to your inbox. Using the API keys, you can access and test your use case via the Finzly Connect APIs.