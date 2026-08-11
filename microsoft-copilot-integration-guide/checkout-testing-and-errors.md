---
description: Understand payment handling, validation, and shopper error recovery.
---

# Checkout, testing, and errors

### Payment handling

ESW handles Adyen payments through a secure token-based flow. Adyen provides the payment token. ESW maps the token to the shopper conversation, authorizes payment, and returns the checkout outcome.

### Validation and testing

ESW validates the checkout services against the manifest. Testing confirms UCP actions perform efficiently and product data synchronizes correctly to merchant centers.

### Checkout service errors

ESW separates shopper-correctable issues from ESW-managed issues. Shoppers receive guidance for correctable details. ESW resolves catalog, authentication, capacity, and infrastructure issues behind the scenes.

| Scenario                                  | Who handles it                    | Shopper experience                                              |
| ----------------------------------------- | --------------------------------- | --------------------------------------------------------------- |
| Invalid personal details                  | Shopper, prompted by the AI agent | Correct and resubmit details.                                   |
| Unsupported delivery country              | Shopper, prompted by the AI agent | Choose a supported country.                                     |
| Product catalog or pricing data issue     | ESW                               | Hidden from the shopper. ESW resolves it.                       |
| Authentication or permissions failure     | ESW                               | ESW adapter handles it. No action required.                     |
| Rate limiting or temporary capacity issue | ESW                               | Automatic retry after a short delay.                            |
| Infrastructure or integration failure     | ESW                               | A graceful message appears. ESW resolves it.                    |
| Minor data formatting issue               | ESW                               | ESW silently corrects it where possible.                        |
| Payment declined                          | ESW                               | A graceful message reflects the failure reason.                 |
| 3DS or fraud challenge required           | Shopper and ESW                   | Complete the challenge, then resume the same checkout session.  |
| Unsupported payment method                | Shopper, prompted by the AI agent | Choose a supported method for the market.                       |
| Item out of stock at checkout             | Shopper and ESW                   | Remove the item or choose an alternative. ESW refreshes totals. |
| Address validation failure                | Shopper, prompted by the AI agent | Correct the specified field before retrying.                    |
