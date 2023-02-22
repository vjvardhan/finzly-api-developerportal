---
title: Sandbox and Testing
---

## **Getting started with Finzly Connect API**

Let your imagination and creativity run wild as you build your embedded experience to delight your customers. We have designed an intuitive sandbox that is as self-service as possible, so that you can begin building using the blocks that Finzly Connect provides.

### **Sandbox access:**

Our sandbox provides a test environment where you can start testing and experiencing our APIs to manage accounts, payments and more. To request access to our sandbox environment, submit your information at [**https://finzly.com/api-access**](https://finzly.com/api-access). For regulatory, suitability evaluation and validation purposes, our team must approve access. 


### **Authentication**

Our APIs use oAuth 2.0 authentication protocol to provide the secure access. You will use our API keys with grant type “Client Credentials” to fetch an access token. This token is digitally signed and contains access information such as user role mapping etc. Access token is a short-lived token (30 sec). To authenticate and authorize your API calls, you will have to pass the access token in authorization header with “bearer” prefix.

<br>

![image info](./images/auth.png)

<br>

**Sample Auth Request**
```yaml Before 

curl -X POST [URL] 
-H "Content-Type: application/x-www-form-urlencoded" 
-H 'Authorization: Basic [Base64(apikey:apisecert)]' 
-d 'grant_type=client_credentials'

```

**Sample Auth Response**

```yaml Before 
{
 "access_token": "",
 "expires_in": 14400,
 "refresh_expires_in": 1800,
 "refresh_token":"",
 "token_type": "bearer",
}

```

Note: Our support team creates an API key and secert for you. Using the API credentials, you can access the Finzly Connect APIs.
