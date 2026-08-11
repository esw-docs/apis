---
description: Configure the UCP profile for agent-led ESW checkout.
---

# UCP profile setup

Enable your UCP profile so Microsoft Copilot, Google Gemini, and Shopify assistants can find products. Agents route qualified shoppers into ESW checkout.

ESW pushes catalog changes to Microsoft Merchant Center. This avoids relying on site crawling for accurate discovery results.

Microsoft Merchant Center creates searchable indexes from your product data. Agents check relevance, price, and availability before creating checkout sessions.

### Host the UCP profile

Your UCP profile is also called the UCP well-known file. Host the manifest JSON on your domain. It tells agents which commerce actions your brand supports. It also connects agents to the ESW checkout API.

The January 23, 2026 UCP specification supports these checkout session actions:

* Create
* Update
* Retrieve and cancel

ESW completes the order and returns the order number and status. The standard post-purchase journey continues through confirmation emails, fulfilment, customer service, tracking, and returns.

### Example UCP well-known file

{% code expandable="true" %}
```json
{
  "ucp": {
    "version": "2026-01-23",
    "services": {
      "dev.ucp.shopping": [
        {
          "version": "2026-01-23",
          "spec": "https://ucp.dev/specification/overview",
          "transport": "rest",
          "endpoint": "https://checkout-acp-api.test.eshopworld.net/UCP/QAUQAU",
          "schema": "https://ucp.dev/2026-01-23/services/shopping/openapi.json"
        }
      ]
    },
    "capabilities": {
      "dev.ucp.shopping.checkout": [
        {
          "version": "2026-01-23",
          "spec": "https://ucp.dev/specification/checkout",
          "schema": "https://ucp.dev/2026-01-23/schemas/shopping/checkout.json",
          "extends": null,
          "config": null
        }
      ],
      "dev.ucp.shopping.fulfillment": [
        {
          "version": "2026-01-23",
          "spec": "https://ucp.dev/specification/fulfillment",
          "schema": "https://ucp.dev/2026-01-23/schemas/shopping/fulfillment.json",
          "extends": "dev.ucp.shopping.checkout",
          "config": null
        }
      ]
    },
    "payment_handlers": {
      "com.adyen": [
        {
          "id": "adyen-card-tokenization",
          "version": "2026-01-23",
          "spec": "https://ucp.dev/specification/payment-handler-guide",
          "config_schema": "https://ucp.dev/2026-01-23/handlers/tokenization/openapi.json",
          "instrument_schemas": [
            "https://ucp.dev/2026-01-23/handlers/tokenization/schemas/card_instrument.json"
          ],
          "config": {
            "environment": "test",
            "public_merchant_id": "e8b29c2e-dd09-48f3-949e-f63fbb416041"
          }
        }
      ]
    }
  },
  "signing_keys": [
    {
      "kid": "ucpgo_2025",
      "kty": "EC",
      "crv": "P-256",
      "x": "WbbXwVYGdJoP4Xm3qCkGvBRcRvKtEfXDbWvPzpPS8LA",
      "y": "sP4jHHxYqC89HBo8TjrtVOAGHfJDflYxw7MFMxuFMPY",
      "use": "sig",
      "alg": "ES256"
    }
  ]
}
```
{% endcode %}
