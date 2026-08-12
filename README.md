# Gift Card

## Split payments (2 gift cards + credit card)

A GoCasual checkout in Germany with the following payment structure

| Line                                         | Amount       |
| -------------------------------------------- | ------------ |
| Description of product one (Qty 1, Blk, M)   | 50.00 €      |
| Description of product Two (Qty 1, Blk, M)   | 50.00 €      |
| Description of product Three (Qty 1, Blk, M) | 40.00 €      |
| Items subtotal                               | **140.00 €** |
| STANDARD Delivery                            | 5.99 €       |
| Gift Card 1 (Card \*\*\*\*0000)              | −50.00 €     |
| Gift Card 2 (Card \*\*\*\*0000)              | −50.00 €     |
| **Balance paid by card**                     | **45.99 €**  |
| **Full order total**                         | **145.99 €** |

Two gift cards of 50.00 € each (both fully depleted — 0.00 € balance remaining) cover 100.00 € of the 145.99 € order. The remaining 45.99 € is charged to a credit card. The billing address is the same as the delivery address (checkbox ticked).

***

{% hint style="info" %}
Gift cards are payment instruments, not discounts. The full order value (145.99 €) is the `checkoutTotal` — split across three payment records:
{% endhint %}

```
Gift Card 1:   50.00 €
Gift Card 2:   50.00 €
Credit Card: + 45.99 €
             ─────────
Total:         145.99 €  ==  checkoutTotal.shopper.amount
```

`paymentDetails` carries the first gift card as the primary payment. `paymentRecords` carries all three instruments — both gift cards and the credit card — including the primary.

***

### Order Confirmation Request Sample

<pre class="language-json" data-expandable="true"><code class="lang-json">{
  "retailerCartId":        "CART-DE-2024-78542",
  "eShopWorldOrderNumber": "ESW-20240605-00078542",
  "deliveryCountryIso":    "DE",
  "cartType":              "Standard",

<strong>  "checkoutTotal": {
</strong><strong>    "retailer": { "currency": "EUR", "amount": "145.99" },
</strong><strong>    "shopper":  { "currency": "EUR", "amount": "145.99" }
</strong>  },

  "paymentDetails": {
    "method":     "GiftCard",
    "time":       "2024-06-05T10:14:00.000Z",
    "amountPaid": 50.00,
    "ticketDetails": {
      "number": "****0000-1"
    }
  },

<strong>  "paymentRecords": [
</strong><strong>    {
</strong><strong>      "method":     "GiftCard",
</strong><strong>      "time":       "2024-06-05T10:14:00.000Z",
</strong><strong>      "amountPaid": 50.00,
</strong><strong>      "ticketDetails": {
</strong><strong>        "number": "****0000-1"
</strong>      }
    },
    {
<strong>      "method":     "GiftCard",
</strong><strong>      "time":       "2024-06-05T10:14:05.000Z",
</strong><strong>      "amountPaid": 50.00,
</strong><strong>      "ticketDetails": {
</strong><strong>        "number": "****0000-2"
</strong>      }
    },
    {
<strong>      "method":          "Card",
</strong><strong>      "methodCardBrand": "Visa",
</strong><strong>      "time":            "2024-06-05T10:14:22.000Z",
</strong><strong>      "amountPaid":      45.99
</strong>    }
  ],

  "lineItems": [
    {
      "lineItemId": "1",
      "quantity":   1,
      "estimatedDeliveryDate": {},
      "product": {
        "productCode": "PROD-001",
        "title":       "Description of product one",
        "description": "Description of product one",
        "color":       "Blk",
        "size":        "M",
        "productUnitPriceInfo": {
          "price": {
            "retailer": { "currency": "EUR", "amount": "50.00" },
            "shopper":  { "currency": "EUR", "amount": "50.00" }
          }
        }
      },
      "charges": {
        "subTotal": {
          "retailer": { "currency": "EUR", "amount": "50.00" },
          "shopper":  { "currency": "EUR", "amount": "50.00" }
        },
        "subTotalBeforeTaxesAndCartDiscountsApplied": {
          "retailer": { "currency": "EUR", "amount": "50.00" },
          "shopper":  { "currency": "EUR", "amount": "50.00" }
        }
      }
    },
    {
      "lineItemId": "2",
      "quantity":   1,
      "estimatedDeliveryDate": {},
      "product": {
        "productCode": "PROD-002",
        "title":       "Description of product Two",
        "description": "Description of product Two",
        "color":       "Blk",
        "size":        "M",
        "productUnitPriceInfo": {
          "price": {
            "retailer": { "currency": "EUR", "amount": "50.00" },
            "shopper":  { "currency": "EUR", "amount": "50.00" }
          }
        }
      },
      "charges": {
        "subTotal": {
          "retailer": { "currency": "EUR", "amount": "50.00" },
          "shopper":  { "currency": "EUR", "amount": "50.00" }
        },
        "subTotalBeforeTaxesAndCartDiscountsApplied": {
          "retailer": { "currency": "EUR", "amount": "50.00" },
          "shopper":  { "currency": "EUR", "amount": "50.00" }
        }
      }
    },
    {
      "lineItemId": "3",
      "quantity":   1,
      "estimatedDeliveryDate": {},
      "product": {
        "productCode": "PROD-003",
        "title":       "Description of product Three",
        "description": "Description of product Three",
        "color":       "Blk",
        "size":        "M",
        "productUnitPriceInfo": {
          "price": {
            "retailer": { "currency": "EUR", "amount": "40.00" },
            "shopper":  { "currency": "EUR", "amount": "40.00" }
          }
        }
      },
      "charges": {
        "subTotal": {
          "retailer": { "currency": "EUR", "amount": "40.00" },
          "shopper":  { "currency": "EUR", "amount": "40.00" }
        },
        "subTotalBeforeTaxesAndCartDiscountsApplied": {
          "retailer": { "currency": "EUR", "amount": "40.00" },
          "shopper":  { "currency": "EUR", "amount": "40.00" }
        }
      }
    }
  ],

  "charges": {
    "total": {
      "retailer": { "currency": "EUR", "amount": "145.99" },
      "shopper":  { "currency": "EUR", "amount": "145.99" }
    },
    "totalBeforeTaxesAndCartDiscountsApplied": {
      "retailer": { "currency": "EUR", "amount": "140.00" },
      "shopper":  { "currency": "EUR", "amount": "140.00" }
    },
    "delivery": {
      "retailer": { "currency": "EUR", "amount": "5.99" },
      "shopper":  { "currency": "EUR", "amount": "5.99" }
    }
  },

  "deliveryOption": {
    "deliveryOption": "STD_DE"
  },

  "contactDetails": [
    {
      "contactDetailType": "IsDelivery",
      "firstName":   "Bob",
      "lastName":    "German",
      "address1":    "Tiergartenstrabe 17",
      "address2":    "ravelin-green",
      "city":        "Berlin",
      "postalCode":  "10785",
      "country":     "DE",
      "email":       "test@greendomain.com",
      "telephone":   "+4930257950",
      "isSelected":  true,
      "isDefault":   false,
      "saveToProfile": false,
      "status":      "Added"
    },
    {
      "contactDetailType": "IsPayment",
      "firstName":   "Bob",
      "lastName":    "German",
      "address1":    "Tiergartenstrabe 17",
      "address2":    "ravelin-green",
      "city":        "Berlin",
      "postalCode":  "10785",
      "country":     "DE",
      "isSelected":  true,
      "isDefault":   false,
      "saveToProfile": false,
      "status":      "Added"
    }
  ]
}
</code></pre>

***

#### `checkoutTotal` — 145.99 €, not 45.99 €

The checkout total is the **full order value** (140.00 items + 5.99 delivery = **145.99 €**), not the 45.99 € the shopper sees as the "balance to pay on this order." The gift cards are payment instruments that contribute to covering this full total — they are not discounts that reduce it.

```
checkoutTotal.shopper.amount = "145.99"   ← full order value
                                           NOT "45.99" (balance after gift cards)
```

This is required for the payment reconciliation: the sum of all `paymentRecords[n].amountPaid` must equal `checkoutTotal.shopper.amount`.

#### `paymentDetails` — first gift card as primary

`paymentDetails` holds the first gift card as the primary payment instrument. The entry in `paymentDetails` must be duplicated as the first entry in `paymentRecords`.

#### `paymentRecords` — all three instruments

Three entries cover the full 145.99 €:

| Entry | Method                    | Amount         |
| ----- | ------------------------- | -------------- |
| 1     | GiftCard (\*\*\*\*0000-1) | 50.00 €        |
| 2     | GiftCard (\*\*\*\*0000-2) | 50.00 €        |
| 3     | Card (Visa)               | 45.99 €        |
|       |                           | **`145.99 €`** |

#### `ticketDetails.number` — distinguishing the two gift cards

Both cards show as `****0000` in the UI — the last four digits are the same. Without `ticketDetails.number`, the two `paymentRecords` entries are identical and indistinguishable in ESW's order record. Using a suffix (`-1`, `-2`) or the actual masked card number as returned by your payment processor is the minimum needed to differentiate them.

If your system has access to more gift card metadata, include `expirationDate` as well:

```json
"ticketDetails": {
  "number":         "GC-XXXX-YYYY-0000",
  "expirationDate": "2025-12-31"
}
```

#### `amountPaid` — number, not string

`amountPaid` across all payment records is a `number` type (double). This is the opposite of the `amount` field inside `checkoutTotal` and `charges`, which are strings.

#### `charges.total` must equal `checkoutTotal`

Both must be 145.99 €:

```json
"checkoutTotal": {
  "shopper": { "currency": "EUR", "amount": "145.99" }
},
"charges": {
  "total": {
    "shopper": { "currency": "EUR", "amount": "145.99" }
  }
}
```

#### `charges.delivery` — 5.99 € as a charge, not a deduction

Delivery is a charge field, not a separate line in the cart discount sense. It contributes to `charges.total`:

```
charges.totalBeforeTaxesAndCartDiscountsApplied:  140.00
+ charges.delivery:                               +  5.99
                                                  ───────
charges.total:                                    145.99  
```

#### `contactDetails` — two entries because billing is same as delivery

The "Billing address same as delivery address" checkbox in the UI means both contact detail types carry identical address data. Two separate entries are needed — `IsDelivery` and `IsPayment` — because the API distinguishes them by `contactDetailType`.

The `IsPayment` entry omits `email` and `telephone` since those are delivery-specific fields not typically required on a billing address. Include them if your integration agreement requires it.

#### `deliveryOption.deliveryOption` — the ESW delivery code

"STANDARD Delivery" — the code (`"STD_DE"` in this example) usually ESW-configured delivery option code for standard delivery to Germany, agreed at onboarding. Replace with your actual configured code.

#### Reconciliation Summary

```
paymentRecords[0].amountPaid   50.00  (Gift Card 1)
paymentRecords[1].amountPaid   50.00  (Gift Card 2)
paymentRecords[2].amountPaid + 45.99  (Card)
                              ───────
Sum:                          145.99
checkoutTotal.shopper.amount: 145.99  

charges.total.shopper.amount: 145.99  
checkoutTotal.shopper.amount: 145.99  

lineItem subTotal sum:  50.00 + 50.00 + 40.00 = 140.00
+ charges.delivery:                            +  5.99
= charges.total:                               145.99  
```

***

## Single gift card (single gift card, full payment)

A GoCasual checkout in Germany where a single gift card covers the **entire order** — items plus delivery. The cart total shows as **Free** and the balance to pay is **0.00 €**. The gift card has a remaining balance of 14.01 € after the purchase.

| Line                                  | Amount            |
| ------------------------------------- | ----------------- |
| Item (Blk, M)                         | 30.00 €           |
| STANDARD Delivery                     | 5.99 €            |
| **Order total**                       | **35.99 €**       |
| Gift Card (Card \*\*\*\*0000) applied | −35.99 €          |
| **Balance to pay**                    | **0.00 € (Free)** |
| Gift card balance remaining           | 14.01 €           |

The gift card held 50.00 €. After covering the 35.99 € order, 14.01 € remains on the card (50.00 − 35.99 = 14.01). No payment is collected, the gift card absorbs the full cost.

***

With a single gift card covering the entire order, `paymentDetails` holds the gift card as the sole payment instrument. `paymentRecords` is not required — there is only one payment method.

The `checkoutTotal` is the **full order value** (35.99 €), not 0.00 €. The gift card is a payment instrument, not a discount. The reconciliation rule still applies:

```
paymentDetails.amountPaid  ==  checkoutTotal.shopper.amount
       35.99               ==       35.99                    
```

{% hint style="info" %}
`cartType` remains `"Standard"` — a real monetary transaction took place via the gift card. `cartType: "ZeroValue"` is reserved for complimentary orders where no payment instrument of any kind was used.
{% endhint %}

***

### Order Confirmation Request Sample

{% code expandable="true" %}
```json
{
  "retailerCartId":        "CART-DE-2024-78543",
  "eShopWorldOrderNumber": "ESW-20240605-00078543",
  "deliveryCountryIso":    "DE",
  "cartType":              "Standard",

  "checkoutTotal": {
    "retailer": { "currency": "EUR", "amount": "35.99" },
    "shopper":  { "currency": "EUR", "amount": "35.99" }
  },

  "paymentDetails": {
    "method":     "GiftCard",
    "time":       "2024-06-05T10:22:00.000Z",
    "amountPaid": 35.99,
    "ticketDetails": {
      "number": "****0000"
    }
  },

  "lineItems": [
    {
      "lineItemId": "1",
      "quantity":   1,
      "estimatedDeliveryDate": {},
      "product": {
        "productCode": "PROD-001",
        "title":       "Description of product",
        "description": "Description of product",
        "color":       "Blk",
        "size":        "M",
        "productUnitPriceInfo": {
          "price": {
            "retailer": { "currency": "EUR", "amount": "30.00" },
            "shopper":  { "currency": "EUR", "amount": "30.00" }
          }
        }
      },
      "charges": {
        "subTotal": {
          "retailer": { "currency": "EUR", "amount": "30.00" },
          "shopper":  { "currency": "EUR", "amount": "30.00" }
        },
        "subTotalBeforeTaxesAndCartDiscountsApplied": {
          "retailer": { "currency": "EUR", "amount": "30.00" },
          "shopper":  { "currency": "EUR", "amount": "30.00" }
        }
      }
    }
  ],

  "charges": {
    "total": {
      "retailer": { "currency": "EUR", "amount": "35.99" },
      "shopper":  { "currency": "EUR", "amount": "35.99" }
    },
    "totalBeforeTaxesAndCartDiscountsApplied": {
      "retailer": { "currency": "EUR", "amount": "30.00" },
      "shopper":  { "currency": "EUR", "amount": "30.00" }
    },
    "delivery": {
      "retailer": { "currency": "EUR", "amount": "5.99" },
      "shopper":  { "currency": "EUR", "amount": "5.99" }
    }
  },

  "deliveryOption": {
    "deliveryOption": "STD_DE"
  },

  "contactDetails": [
    {
      "contactDetailType": "IsDelivery",
      "firstName":   "Bob",
      "lastName":    "German",
      "address1":    "Tiergartenstrabe 17",
      "address2":    "ravelin-green",
      "city":        "Berlin",
      "postalCode":  "10785",
      "country":     "DE",
      "email":       "test@greendomain.com",
      "telephone":   "+4930257950",
      "isSelected":  true,
      "isDefault":   false,
      "saveToProfile": false,
      "status":      "Added"
    },
    {
      "contactDetailType": "IsPayment",
      "firstName":   "Bob",
      "lastName":    "German",
      "address1":    "Tiergartenstrabe 17",
      "address2":    "ravelin-green",
      "city":        "Berlin",
      "postalCode":  "10785",
      "country":     "DE",
      "isSelected":  true,
      "isDefault":   false,
      "saveToProfile": false,
      "status":      "Added"
    }
  ]
}
```
{% endcode %}

***

#### `checkoutTotal` — 35.99 €, not 0.00 €

The UI shows "Total: Free" but the API `checkoutTotal` must be the full order value — **35.99 €** — because that is the amount the gift card actually paid. The "Free" label in the UI reflects the shopper's cash outlay (zero), not the value of the transaction.

Sending `checkoutTotal.shopper.amount: "0.00"` would break the payment reconciliation, because `paymentDetails.amountPaid` is 35.99.

```
checkoutTotal.shopper.amount: "35.99"  ← full order value paid by gift card
                                          NOT "0.00" despite UI showing "Free"
```

#### `paymentDetails` only

A single payment instrument means having `paymentDetails` only is valid. `paymentRecords` is required when more than one payment method is used.

```json
"paymentDetails": {
  "method":     "GiftCard",
  "time":       "2024-06-05T10:22:00.000Z",
  "amountPaid": 35.99
}
```

{% tabs %}
{% tab title="Valid — paymentRecords omitted" %}
```json
"paymentDetails": {
  "method":     "GiftCard",
  "time":       "2024-06-05T10:22:00.000Z",
  "amountPaid": 35.99,
  "ticketDetails": {
    "number": "****0000"
  }
}
```

No `paymentRecords` field at all. This is correct and complete for a single gift card.
{% endtab %}

{% tab title="Also valid — paymentRecords included with one entry" %}
```json
"paymentDetails": {
  "method":     "GiftCard",
  "time":       "2024-06-05T10:22:00.000Z",
  "amountPaid": 35.99
},
"paymentRecords": [
  {
    "method":     "GiftCard",
    "time":       "2024-06-05T10:22:00.000Z",
    "amountPaid": 35.99
  }
]
```

Including `paymentRecords` with a single entry matching `paymentDetails` is also accepted. Some include it consistently for uniformity — both approaches work.
{% endtab %}
{% endtabs %}

#### `amountPaid` — 35.99, not 50.00

`amountPaid` is the amount **applied to this order**, not the total balance on the gift card. The card holds 50.00 € but only 35.99 € was applied. The remaining 14.01 € stays on the card and is not relevant to this confirmation.

```
Gift card balance:          50.00 €
Amount applied to order:  − 35.99 €
Remaining on card:          14.01 €  ← not included in the request
```

#### `ticketDetails` — optional but recommended

`ticketDetails.number` carries the card's reference identifier. Even for a single gift card it is good practice to include it — it provides an audit trail if the order is queried later or a refund is needed back to the card.

```json
"ticketDetails": {
  "number": "****0000"
}
```

If your system has the full unmasked card reference or the gift card's expiry date, include those too:

```json
"ticketDetails": {
  "number":         "GC-XXXX-YYYY-0000",
  "expirationDate": "2025-12-31"
}
```

#### `cartType` — `"Standard"`, not `"ZeroValue"`

`cartType: "ZeroValue"` is for complimentary orders where no payment was made at all — promotional giveaways, staff samples, or orders covered by an ESW-level adjustment. A gift card is a real payment instrument; the transaction has genuine monetary value even though the shopper's cash outlay was zero.

Use `"Standard"` for any order where a gift card covered the cost.

#### `charges` structure

Single item, delivery charge, no discounts:

```
charges.totalBeforeTaxesAndCartDiscountsApplied:  30.00   (item only)
+ charges.delivery:                               + 5.99
                                                  ───────
charges.total:                                    35.99  
```

#### Reconciliation Summary

```
paymentDetails.amountPaid:    35.99
checkoutTotal.shopper.amount: 35.99  

charges.total.shopper.amount: 35.99
checkoutTotal.shopper.amount: 35.99  

lineItem subTotal:  30.00
+ charges.delivery: 5.99
= charges.total:   35.99  
```

***

## Multiple gift cards (2 gift cards, full payment)

A GoCasual checkout in Germany where **two gift cards together cover the entire order** — items plus delivery with no credit or debit card involved. The total shows as **Free** and the balance to pay is **0.00 €**.

| Line                                    | Amount            |
| --------------------------------------- | ----------------- |
| Items                                   | 90.00 €           |
| STANDARD Delivery                       | 5.99 €            |
| **Order total**                         | **95.99 €**       |
| Gift Card 1 (Card \*\*\*\*0000) applied | −50.00 €          |
| Gift Card 2 (Card \*\*\*\*0000) applied | −45.99 €          |
| **Balance to pay**                      | **0.00 € (Free)** |

**Gift card balances after purchase:**

| Card                       | Applied to order | Remaining balance       | Started with |
| -------------------------- | ---------------- | ----------------------- | ------------ |
| Gift Card 1 (\*\*\*\*0000) | 50.00 €          | 0.00 € — fully depleted | 50.00 €      |
| Gift Card 2 (\*\*\*\*0000) | 45.99 €          | 4.01 € — partially used | 50.00 €      |

Gift Card 1 was used in full (50.00 − 50.00 = 0.00). Gift Card 2 had 50.00 € on it; 45.99 € was applied, leaving 4.01 € on the card (50.00 − 45.99 = 4.01 ).

***

Two gift cards, no third payment instrument. `paymentDetails` carries the first gift card as primary. `paymentRecords` carries both — required because more than one payment method was used. No credit card entry exists.

```
Gift Card 1:  50.00 €
Gift Card 2:+ 45.99 €
            ─────────
Total:        95.99 €  ==  checkoutTotal.shopper.amount  
```

***

### Order Confirmation Request Sample

{% code expandable="true" %}
```json
{
  "retailerCartId":        "CART-DE-2024-78544",
  "eShopWorldOrderNumber": "ESW-20240605-00078544",
  "deliveryCountryIso":    "DE",
  "cartType":              "Standard",
  "checkoutTotal": {
    "retailer": { "currency": "EUR", "amount": "95.99" },
    "shopper":  { "currency": "EUR", "amount": "95.99" }
  },
  "paymentDetails": {
    "method":     "GiftCard",
    "time":       "2024-06-05T10:30:00.000Z",
    "amountPaid": 50.00,
    "ticketDetails": {
      "number": "****0000-1"
    }
  },
  "paymentRecords": [
    {
      "method":     "GiftCard",
      "time":       "2024-06-05T10:30:00.000Z",
      "amountPaid": 50.00,
      "ticketDetails": {
        "number": "****0000-1"
      }
    },
    {
      "method":     "GiftCard",
      "time":       "2024-06-05T10:30:05.000Z",
      "amountPaid": 45.99,
      "ticketDetails": {
        "number": "****0000-2"
      }
    }
  ],
  "lineItems": [
    {
      "lineItemId": "1",
      "quantity":   1,
      "estimatedDeliveryDate": {},
      "product": {
        "productCode": "PROD-002",
        "title":       "Description of Product Two",
        "description": "Description of Product Two",
        "color":       "Blk",
        "size":        "M",
        "productUnitPriceInfo": {
          "price": {
            "retailer": { "currency": "EUR", "amount": "40.00" },
            "shopper":  { "currency": "EUR", "amount": "40.00" }
          }
        }
      },
      "charges": {
        "subTotal": {
          "retailer": { "currency": "EUR", "amount": "40.00" },
          "shopper":  { "currency": "EUR", "amount": "40.00" }
        },
        "subTotalBeforeTaxesAndCartDiscountsApplied": {
          "retailer": { "currency": "EUR", "amount": "40.00" },
          "shopper":  { "currency": "EUR", "amount": "40.00" }
        }
      }
    },
    {
      "lineItemId": "2",
      "quantity":   1,
      "estimatedDeliveryDate": {},
      "product": {
        "productCode": "PROD-005",
        "title":       "Description of Product Five",
        "description": "Description of Product Five",
        "color":       "Nvy",
        "size":        "M",
        "productUnitPriceInfo": {
          "price": {
            "retailer": { "currency": "EUR", "amount": "50.00" },
            "shopper":  { "currency": "EUR", "amount": "50.00" }
          }
        }
      },
      "charges": {
        "subTotal": {
          "retailer": { "currency": "EUR", "amount": "50.00" },
          "shopper":  { "currency": "EUR", "amount": "50.00" }
        },
        "subTotalBeforeTaxesAndCartDiscountsApplied": {
          "retailer": { "currency": "EUR", "amount": "50.00" },
          "shopper":  { "currency": "EUR", "amount": "50.00" }
        }
      }
    }
  ],
  "charges": {
    "total": {
      "retailer": { "currency": "EUR", "amount": "95.99" },
      "shopper":  { "currency": "EUR", "amount": "95.99" }
    },
    "totalBeforeTaxesAndCartDiscountsApplied": {
      "retailer": { "currency": "EUR", "amount": "90.00" },
      "shopper":  { "currency": "EUR", "amount": "90.00" }
    },
    "delivery": {
      "retailer": { "currency": "EUR", "amount": "5.99" },
      "shopper":  { "currency": "EUR", "amount": "5.99" }
    }
  },
  "deliveryOption": {
    "deliveryOption": "STD_DE"
  },
  "contactDetails": [
    {
      "contactDetailType": "IsDelivery",
      "firstName":   "Bob",
      "lastName":    "German",
      "address1":    "Tiergartenstrabe 17",
      "address2":    "ravelin-green",
      "city":        "Berlin",
      "postalCode":  "10785",
      "country":     "DE",
      "email":       "test@greendomain.com",
      "telephone":   "+4930257950",
      "isSelected":  true,
      "isDefault":   false,
      "saveToProfile": false,
      "status":      "Added"
    },
    {
      "contactDetailType": "IsPayment",
      "firstName":   "Bob",
      "lastName":    "German",
      "address1":    "Tiergartenstrabe 17",
      "address2":    "ravelin-green",
      "city":        "Berlin",
      "postalCode":  "10785",
      "country":     "DE",
      "isSelected":  true,
      "isDefault":   false,
      "saveToProfile": false,
      "status":      "Added"
    }
  ]
}
```
{% endcode %}

***

#### `checkoutTotal` — 95.99 €, not 0.00 €

Same rule as before: `checkoutTotal` is the full order value, not the shopper's cash outlay. The gift cards paid 95.99 € — that is the transaction value.

```
Items:     90.00 €
Delivery: + 5.99 €
          ─────────
Total:     95.99 €  ←  checkoutTotal.shopper.amount
```

#### `paymentDetails` — first gift card, 50.00 €

The larger (and fully depleted) gift card goes in `paymentDetails` as the primary. Either card could be primary.

#### `paymentRecords` — two entries, no card

`paymentRecords` is required here because two payment instruments were used. There is no credit card entry — only the two gift cards.

```json
"paymentRecords": [
  { "method": "GiftCard", "amountPaid": 50.00 },   // GC1 — fully depleted
  { "method": "GiftCard", "amountPaid": 45.99 }    // GC2 — 4.01 € remaining
]
```

#### `amountPaid` reflects applied amount, not card balance

|                  | Gift Card 1                | Gift Card 2                |
| ---------------- | -------------------------- | -------------------------- |
| Starting balance | 50.00 €                    | 50.00 €                    |
| Applied to order | **50.00 €** ← `amountPaid` | **45.99 €** ← `amountPaid` |
| Remaining        | 0.00 €                     | 4.01 €                     |

The remaining balances (0.00 and 4.01) are not fields anywhere in the schema and do not affect the request.

#### `ticketDetails.number` — essential for two identical-looking cards

Both cards display as `****0000` in the UI. Without `ticketDetails.number`, the two `paymentRecords` entries are structurally identical and cannot be distinguished in ESW's order record. Use suffixes (`-1`, `-2`) if your system only has the masked number, or the full card reference if available.

```json
{ "ticketDetails": { "number": "****0000-1" } }  // GC1 — 50.00 €, fully used
{ "ticketDetails": { "number": "****0000-2" } }  // GC2 — 45.99 € used, 4.01 remaining
```

#### `cartType` — `"Standard"`

Two gift cards covering the full cost is still a `"Standard"` order — real monetary value was exchanged via two payment instruments. `"ZeroValue"` is not applicable.

#### Items total is 90.00 €

The `lineItems` array and `charges.totalBeforeTaxesAndCartDiscountsApplied` must account for the full 90.00 €.

#### `charges` structure

```
charges.totalBeforeTaxesAndCartDiscountsApplied:  90.00
+ charges.delivery:                               + 5.99
                                                  ───────
charges.total:                                    95.99  
```

***

#### Reconciliation Summary

```
paymentRecords[0].amountPaid:   50.00  (GC1 — depleted)
paymentRecords[1].amountPaid: + 45.99  (GC2 — 4.01 remaining)
                              ──────
Sum:                           95.99
checkoutTotal.shopper.amount:  95.99  

charges.total.shopper.amount:  95.99
checkoutTotal.shopper.amount:  95.99  

lineItems subtotal:  90.00
+ delivery:          5.99
= charges.total:    95.99  
```

***
