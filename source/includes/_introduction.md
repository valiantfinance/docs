## Introduction

Welcome to the Valiant API!

The Valiant API is a [RESTful](http://en.wikipedia.org/wiki/Representational_State_Transfer) API with predictable, resource-oriented URLs, and uses semantic HTTP response codes to indicate API errors. Our API supports [cross-origin resource sharing (CORS)](http://en.wikipedia.org/wiki/Cross-origin_resource_sharing), allowing you to securely consume our API from any client-side web application. [JSON](http://www.json.org/) is returned by all resource related API responses and all API requests must be made over [`HTTPS`](http://en.wikipedia.org/wiki/HTTP_Secure). The API follows version 1.0 of the [`json:api`](http://jsonapi.org/) specification for all resource related requests and responses.

<aside class="notice">
  To get started with our API please send through a request to <a href="mailto:dev@valiant.finance">dev@valiant.finance</a> with your details, your company's details, and why you would like to use the API and we will onboard you.
</aside>


## Status

🚦 The status of our producton and sandbox APIs are viewable on our <a href="https://www.valiantstatus.com" target="_blank">Valiant status page.</a>


## Sandbox

As a part of onboarding, we will provide both a set of Sandbox and Production API credentials. All endpoint paths for both APIs are the same; however, the root domain differs as follows:

- **Sandbox** – [`https://mercury-summer.valiant.finance/`](https://mercury-summer.valiant.finance/)
- **Production** – [`https://valiant.finance/`](https://valiant.finance/)

To test the API Sandbox, we recommend using [Postman](https://www.getpostman.com/). We couldn't live without it! 📮

To make life even easier, we have put together a ready-to-go collection of our API end-points. All you need to do is add your credentials, and you're ready to hit the ground running!

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/86abaac4a633772a1416)

To test the API endpoints in our Postman collection, simply:

1. Add your **`X-AUTH-ID`** as the current value of the `id` variable;
2. Add your **`X-AUTH-SIGNED-KEY`** as the current value of the `signed_key` variable; and
3. Ensure you are testing the correct url - either our sandbox [`https://mercury-summer.valiant.finance/`](https://mercury-summer.valiant.finance/) or production [`https://valiant.finance/`](https://valiant.finance/).

Not sure how to generate the **`X-AUTH-ID`** or **`X-AUTH-SIGNED-KEY`** mentioned above? Take a look at the _Authentication_ -> _Headers_ section below.

![alt text](/images/postman-credentials.png)
