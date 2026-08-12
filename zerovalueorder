# Zero Value Order

Zero Value Order (ZVO) enables checkout to support orders with 100% discounts — where the shopper pays nothing.

### Benefits

* Allow shoppers to complete checkout when the order total is `£0`.
* Ensure no payment is captured and no shipping is charged.
* Support finance reconciliation and customs declarations for fully discounted orders.

### Settlement process

* ZVOs appear in a separate settlement report from paid orders.
* ESW pays duties and taxes on retailers' behalf.
* These costs are deducted from retailer settlements.
* Although shoppers pay nothing, the order value must be declared to customs.

### Use Cases <a href="#use-cases-for-zvo" id="use-cases-for-zvo"></a>

| Use case                                                                                                                        | Example                                                                                                        | Expected behavior                                                                                                                                                                                                        |
| ------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| <p><strong>100% discount or promotional order</strong><br>A promotion or coupon reduces the order total to <code>€0</code>.</p> | <p>Product price: <code>€50</code><br>Coupon: 100% off<br>Shipping: Free<br>Total payable: <code>€0</code></p> | <ul><li>Shopper completes checkout without payment details.</li><li>Order is created successfully.<br>Promotion details are recorded for reporting and analytics.</li><li>An order-confirmation email is sent.</li></ul> |
| **Complimentary sample or free gift order:** A retailer offers free samples or promotional gifts without a purchase.            | <p>Free skincare sample<br>Free event merchandise<br>Welcome kit for new customers</p>                         | <ul><li>Shopper places the order without payment.</li><li>Shipping details are collected.</li><li>No shipping fee applies.</li><li>Business rules may limit quantities, such as one sample per customer.</li></ul>       |

### Preorder Sample Payloads

{% tabs %}
{% tab title="100% promotion at cart level" %}
{% code expandable="true" %}

```json
{
  "retailerCartId": "GOC25082115310085US",
  "contactDetails": [
    {
      "contactDetailsType": "IsDeliveryAndPayment",
      "contactDetailsNickName": null,
      "address1": "4493 Austell Road",
      "address2": "",
      "address3": null,
      "city": "Austell",
      "postalCode": "30106",
      "country": "US",
      "email": "test@unitedstates.com",
      "firstName": "Bob",
      "lastName": "American",
      "gender": "None",
      "telephone": "+14044132000",
      "poBox": null,
      "region": "GA"
    }
  ],
  "shopperCurrencyIso": "USD",
  "deliveryCountryIso": "US",
  "shopperCheckoutExperience": null,
  "lineItems": [
    {
      "quantity": 1,
      "product": {
        "description": "Xbox Wireless Controller",
        "imageUrl": "https://staging.spectrumcustomizer.com/api/assets/generated/recipeset/readable/9XURJSBM/view/north",
        "productCode": "123456789",
        "productUnitPriceInfo": {
          "price": {
            "amount": "79.99",
            "currency": "USD"
          }
        },
        "title": "Xbox Wireless Controller"
      }
    },
    {
      "quantity": 1,
      "product": {
        "description": "Xbox Wireless Controller",
        "imageUrl": "https://staging.spectrumcustomizer.com/api/assets/generated/recipeset/readable/9XURJSBM/view/north",
        "productCode": "123456789",
        "productUnitPriceInfo": {
          "price": {
            "amount": "159.99",
            "currency": "USD"
          }
        },
        "title": "Xbox Wireless Controller"
      }
    }
  ],
  "cartDiscountPriceInfo": {
    "price": {
      "currency": "USD",
      "amount": "0.00"
    },
    "discounts": [
      {
        "title": "100% PROMOTION",
        "description": "Discount description",
        "percentage": "100"
      }
    ]
  },
  "retailerCheckoutExperience": {
    "backToCartUrl": null,
    "continueShoppingUrl": null,
    "metadataItems": []
  },
  "retailerDeliveryOptions": [
    {
      "deliveryOption": "POST",
      "title": "Standard",
      "estimatedDeliveryDateToShopper": {
        "dateTo": "2025-09-19T00:00:00Z"
      },
      "retailerDeliveryOptionPriceInfo": {
        "price": {
          "currency": "USD",
          "amount": "0.00"
        }
      }
    }
  ],
  "deliveryOptions": [
    {
      "deliveryOption": "POST",
      "deliveryOptionOverridePriceInfo": {
        "price": {
          "currency": "USD",
          "amount": "0.00"
        }
      }
    }
  ]
}
```

{% endcode %}
{% endtab %}

{% tab title="Full discount at cart level" %}
{% code expandable="true" %}

```json
{
  "retailerCartId": "GOC25082115310085US",
  "contactDetails": [
    {
      "contactDetailsType": "IsDeliveryAndPayment",
      "contactDetailsNickName": null,
      "address1": "4493 Austell Road",
      "address2": "",
      "address3": null,
      "city": "Austell",
      "postalCode": "30106",
      "country": "US",
      "email": "test@unitedstates.com",
      "firstName": "Bob",
      "lastName": "American",
      "gender": "None",
      "telephone": "+14044132000",
      "poBox": null,
      "region": "GA"
    }
  ],
  "shopperCurrencyIso": "USD",
  "deliveryCountryIso": "US",
  "shopperCheckoutExperience": null,
  "lineItems": [
    {
      "quantity": 1,
      "product": {
        "description": "Xbox Wireless Controller",
        "imageUrl": "https://staging.spectrumcustomizer.com/api/assets/generated/recipeset/readable/9XURJSBM/view/north",
        "productCode": "123456789",
        "productUnitPriceInfo": {
          "price": {
            "amount": "79.99",
            "currency": "USD"
          }
        },
        "title": "Xbox Wireless Controller"
      }
    },
    {
      "quantity": 1,
      "product": {
        "description": "Xbox Wireless Controller",
        "imageUrl": "https://staging.spectrumcustomizer.com/api/assets/generated/recipeset/readable/9XURJSBM/view/north",
        "productCode": "123456789",
        "productUnitPriceInfo": {
          "price": {
            "amount": "159.99",
            "currency": "USD"
          }
        },
        "title": "Xbox Wireless Controller"
      }
    }
  ],
  "cartDiscountPriceInfo": {
    "price": {
      "currency": "USD",
      "amount": "0.00"
    },
    "discounts": [
      {
        "beforeDiscount": {
          "amount": "239.98",
          "currency": "USD"
        },
        "discount": {
          "amount": "239.98",
          "currency": "USD"
        }
      }
    ]
  },
  "retailerCheckoutExperience": {
    "backToCartUrl": null,
    "continueShoppingUrl": null,
    "metadataItems": []
  },
  "retailerDeliveryOptions": [
    {
      "deliveryOption": "POST",
      "title": "Standard",
      "estimatedDeliveryDateToShopper": {
        "dateTo": "2025-09-19T00:00:00Z"
      },
      "retailerDeliveryOptionPriceInfo": {
        "price": {
          "currency": "USD",
          "amount": "0.00"
        }
      }
    }
  ],
  "deliveryOptions": [
    {
      "deliveryOption": "POST",
      "deliveryOptionOverridePriceInfo": {
        "price": {
          "currency": "USD",
          "amount": "0.00"
        }
      }
    }
  ]
}
```

{% endcode %}
{% endtab %}

{% tab title="Full discount at item level" %}
{% code expandable="true" %}

```json
{
  "retailerCartId": "GOC25082115310085US",
  "contactDetails": [
    {
      "contactDetailsType": "IsDeliveryAndPayment",
      "contactDetailsNickName": null,
      "address1": "4493 Austell Road",
      "address2": "",
      "address3": null,
      "city": "Austell",
      "postalCode": "30106",
      "country": "US",
      "email": "test@unitedstates.com",
      "firstName": "Bob",
      "lastName": "American",
      "gender": "None",
      "telephone": "+14044132000",
      "poBox": null,
      "region": "GA"
    }
  ],
  "shopperCurrencyIso": "USD",
  "deliveryCountryIso": "US",
  "shopperCheckoutExperience": null,
  "lineItems": [
    {
      "quantity": 1,
      "product": {
        "description": "Xbox Wireless Controller",
        "imageUrl": "https://staging.spectrumcustomizer.com/api/assets/generated/recipeset/readable/9XURJSBM/view/north",
        "productCode": "123456789",
        "productUnitPriceInfo": {
          "discounts": [
            {
              "beforeDiscount": {
                "amount": "79.99",
                "currency": "USD"
              },
              "discount": {
                "amount": "79.99",
                "currency": "USD"
              }
            }
          ],
          "price": {
            "amount": "0.00",
            "currency": "USD"
          }
        },
        "title": "Xbox Wireless Controller"
      }
    },
    {
      "quantity": 1,
      "product": {
        "description": "SUPER Xbox Wireless Controller SUPER",
        "imageUrl": "https://staging.spectrumcustomizer.com/api/assets/generated/recipeset/readable/9XURJSBM/view/north",
        "productCode": "123456789",
        "productUnitPriceInfo": {
          "discounts": [
            {
              "beforeDiscount": {
                "amount": "159.99",
                "currency": "USD"
              },
              "discount": {
                "amount": "159.99",
                "currency": "USD"
              }
            }
          ],
          "price": {
            "amount": "0.00",
            "currency": "USD"
          }
        },
        "title": "Xbox Wireless Controller"
      }
    }
  ],
  "retailerCheckoutExperience": {
    "backToCartUrl": null,
    "continueShoppingUrl": null,
    "metadataItems": []
  },
  "retailerDeliveryOptions": [
    {
      "deliveryOption": "POST",
      "title": "Standard",
      "estimatedDeliveryDateToShopper": {
        "dateTo": "2025-09-19T00:00:00Z"
      },
      "retailerDeliveryOptionPriceInfo": {
        "price": {
          "currency": "USD",
          "amount": "0.00"
        }
      }
    }
  ],
  "deliveryOptions": [
    {
      "deliveryOption": "POST",
      "deliveryOptionOverridePriceInfo": {
        "price": {
          "currency": "USD",
          "amount": "0.00"
        }
      }
    }
  ]
}
```

{% endcode %}
{% endtab %}
{% endtabs %}

### Order Confirmation Sample Payloads

{% tabs %}
{% tab title="100% promotion at cart level" %}
{% code expandable="true" %}

```json
{
  "retailerCartId": "GOC80902115310076US",
  "eShopWorldOrderNumber": "5c9dc22a-78df-4a1b-a498-c9b3fa41c6ce",
  "checkoutTotal": {
    "retailer": {
      "currency": "EUR",
      "amount": "0.00"
    },
    "shopper": {
      "currency": "USD",
      "amount": "0.00"
    }
  },
  "pricingSynchronizationId": null,
  "paymentDetails": {
    "time": "2025-08-29T11:44:51.1800999Z",
    "method": "NoPaymentRequired",
    "methodCardBrand": null,
    "fraudHold": null
  },
  "retailerPromoCodes": [],
  "lineItems": [
    {
      "quantity": 1,
      "product": {
        "productCode": "123456789",
        "hsCode": "6211499090",
        "title": "Xbox Wireless Controller",
        "description": "Xbox Wireless Controller",
        "productUnitPriceInfo": {
          "price": {
            "retailer": {
              "currency": "EUR",
              "amount": "68.54"
            },
            "shopper": {
              "currency": "USD",
              "amount": "79.99"
            }
          },
          "discounts": []
        },
        "imageUrl": "https://staging.spectrumcustomizer.com/api/assets/generated/recipeset/readable/9XURJSBM/view/north",
        "color": null,
        "size": null,
        "isReturnProhibited": null,
        "metadataItems": []
      },
      "estimatedDeliveryDate": {
        "fromRetailer": "2025-09-19T00:00:00Z",
        "fromEShopWorld": null,
        "fromEShopWorldRangeFrom": null,
        "fromEShopWorldRangeTo": null
      },
      "lineItemId": 1,
      "charges": {
        "subTotalBeforeTaxesAndCartDiscountsApplied": {
          "retailer": {
            "currency": "EUR",
            "amount": "68.54"
          },
          "shopper": {
            "currency": "USD",
            "amount": "79.99"
          }
        },
        "subTotalAfterCartDiscount": {
          "retailer": {
            "currency": "EUR",
            "amount": "0.00"
          },
          "shopper": {
            "currency": "USD",
            "amount": "0.00"
          }
        },
        "cartDiscountAttribution": {
          "retailer": {
            "currency": "EUR",
            "amount": "68.54"
          },
          "shopper": {
            "currency": "USD",
            "amount": "79.99"
          }
        },
        "subTotal": {
          "retailer": {
            "currency": "EUR",
            "amount": "0.00"
          },
          "shopper": {
            "currency": "USD",
            "amount": "0.00"
          }
        },
        "uplift": {
          "retailer": {
            "currency": "EUR",
            "amount": "0.00"
          },
          "shopper": {
            "currency": "USD",
            "amount": "0.00"
          }
        },
        "delivery": {
          "retailer": {
            "currency": "EUR",
            "amount": "0.00"
          },
          "shopper": {
            "currency": "USD",
            "amount": "0.00"
          }
        },
        "deliveryDuty": {
          "retailer": {
            "currency": "EUR",
            "amount": "0.00"
          },
          "shopper": {
            "currency": "USD",
            "amount": "0.00"
          }
        },
        "deliveryTaxes": {
          "retailer": {
            "currency": "EUR",
            "amount": "0.00"
          },
          "shopper": {
            "currency": "USD",
            "amount": "0.00"
          }
        },
        "taxes": {
          "retailer": {
            "currency": "EUR",
            "amount": "0.00"
          },
          "shopper": {
            "currency": "USD",
            "amount": "0.00"
          }
        },
        "otherTaxes": {
          "retailer": {
            "currency": "EUR",
            "amount": "0.00"
          },
          "shopper": {
            "currency": "USD",
            "amount": "0.00"
          }
        },
        "administration": {
          "retailer": {
            "currency": "EUR",
            "amount": "0.00"
          },
          "shopper": {
            "currency": "USD",
            "amount": "0.00"
          }
        },
        "duty": {
          "retailer": {
            "currency": "EUR",
            "amount": "0.00"
          },
          "shopper": {
            "currency": "USD",
            "amount": "0.00"
          }
        }
      },
      "metadataItems": [],
      "lineItemZeroValueCharges": {
        "subTotal": {
          "retailer": {
            "currency": "EUR",
            "amount": "68.54"
          },
          "shopper": {
            "currency": "USD",
            "amount": "79.99"
          }
        },
        "taxes": {
          "retailer": {
            "currency": "EUR",
            "amount": "4.11"
          },
          "shopper": {
            "currency": "USD",
            "amount": "4.80"
          }
        },
        "otherTaxes": {
          "retailer": {
            "currency": "EUR",
            "amount": "0.00"
          },
          "shopper": {
            "currency": "USD",
            "amount": "0.00"
          }
        },
        "duty": {
          "retailer": {
            "currency": "EUR",
            "amount": "0.00"
          },
          "shopper": {
            "currency": "USD",
            "amount": "0.00"
          }
        }
      }
    },
    {
      "quantity": 1,
      "product": {
        "productCode": "123456789",
        "hsCode": "6211499090",
        "title": "Xbox Wireless Controller",
        "description": "Xbox Wireless Controller",
        "productUnitPriceInfo": {
          "price": {
            "retailer": {
              "currency": "EUR",
              "amount": "137.09"
            },
            "shopper": {
              "currency": "USD",
              "amount": "159.99"
            }
          },
          "discounts": []
        },
        "imageUrl": "https://staging.spectrumcustomizer.com/api/assets/generated/recipeset/readable/9XURJSBM/view/north",
        "color": null,
        "size": null,
        "isReturnProhibited": null,
        "metadataItems": []
      },
      "estimatedDeliveryDate": {
        "fromRetailer": "2025-09-19T00:00:00Z",
        "fromEShopWorld": null,
        "fromEShopWorldRangeFrom": null,
        "fromEShopWorldRangeTo": null
      },
      "lineItemId": 2,
      "charges": {
        "subTotalBeforeTaxesAndCartDiscountsApplied": {
          "retailer": {
            "currency": "EUR",
            "amount": "137.09"
          },
          "shopper": {
            "currency": "USD",
            "amount": "159.99"
          }
        },
        "subTotalAfterCartDiscount": {
          "retailer": {
            "currency": "EUR",
            "amount": "0.00"
          },
          "shopper": {
            "currency": "USD",
            "amount": "0.00"
          }
        },
        "cartDiscountAttribution": {
          "retailer": {
            "currency": "EUR",
            "amount": "137.09"
          },
          "shopper": {
            "currency": "USD",
            "amount": "159.99"
          }
        },
        "subTotal": {
          "retailer": {
            "currency": "EUR",
            "amount": "0.00"
          },
          "shopper": {
            "currency": "USD",
            "amount": "0.00"
          }
        },
        "uplift": {
          "retailer": {
            "currency": "EUR",
            "amount": "0.00"
          },
          "shopper": {
            "currency": "USD",
            "amount": "0.00"
          }
        },
        "delivery": {
          "retailer": {
            "currency": "EUR",
            "amount": "0.00"
          },
          "shopper": {
            "currency": "USD",
            "amount": "0.00"
          }
        },
        "deliveryDuty": {
          "retailer": {
            "currency": "EUR",
            "amount": "0.00"
          },
          "shopper": {
            "currency": "USD",
            "amount": "0.00"
          }
        },
        "deliveryTaxes": {
          "retailer": {
            "currency": "EUR",
            "amount": "0.00"
          },
          "shopper": {
            "currency": "USD",
            "amount": "0.00"
          }
        },
        "taxes": {
          "retailer": {
            "currency": "EUR",
            "amount": "0.00"
          },
          "shopper": {
            "currency": "USD",
            "amount": "0.00"
          }
        },
        "otherTaxes": {
          "retailer": {
            "currency": "EUR",
            "amount": "0.00"
          },
          "shopper": {
            "currency": "USD",
            "amount": "0.00"
          }
        },
        "administration": {
          "retailer": {
            "currency": "EUR",
            "amount": "0.00"
          },
          "shopper": {
            "currency": "USD",
            "amount": "0.00"
          }
        },
        "duty": {
          "retailer": {
            "currency": "EUR",
            "amount": "0.00"
          },
          "shopper": {
            "currency": "USD",
            "amount": "0.00"
          }
        }
      },
      "metadataItems": [],
      "lineItemZeroValueCharges": {
        "subTotal": {
          "retailer": {
            "currency": "EUR",
            "amount": "137.09"
          },
          "shopper": {
            "currency": "USD",
            "amount": "159.99"
          }
        },
        "taxes": {
          "retailer": {
            "currency": "EUR",
            "amount": "8.23"
          },
          "shopper": {
            "currency": "USD",
            "amount": "9.60"
          }
        },
        "otherTaxes": {
          "retailer": {
            "currency": "EUR",
            "amount": "0.00"
          },
          "shopper": {
            "currency": "USD",
            "amount": "0.00"
          }
        },
        "duty": {
          "retailer": {
            "currency": "EUR",
            "amount": "0.00"
          },
          "shopper": {
            "currency": "USD",
            "amount": "0.00"
          }
        }
      }
    }
  ],
  "cartDiscountPriceInfo": {
    "price": {
      "retailer": {
        "currency": "EUR",
        "amount": "0.00"
      },
      "shopper": {
        "currency": "USD",
        "amount": "0.00"
      }
    },
    "discounts": [
      {
        "title": "PROMOTION",
        "description": "Discount description",
        "discount": {
          "retailer": {
            "currency": "EUR",
            "amount": "205.63"
          },
          "shopper": {
            "currency": "USD",
            "amount": "239.98"
          }
        },
        "beforeDiscount": {
          "retailer": {
            "currency": "EUR",
            "amount": "205.63"
          },
          "shopper": {
            "currency": "USD",
            "amount": "239.98"
          }
        },
        "percentage": "100"
      }
    ]
  },
  "deliveryCountryIso": "US",
  "shopperCheckoutExperience": {
    "shopperCultureLanguageIso": "en-IE",
    "emailMarketingOptIn": null,
    "registeredProfileId": null,
    "saveAddressForNextPurchase": false,
    "metadataItems": [],
    "packagingOption": null
  },
  "retailerCheckoutExperience": {
    "metadataItems": []
  },
  "deliveryOption": null,
  "retailerDeliveryOption": {
    "deliveryOption": "POST",
    "title": "Standard",
    "estimatedDeliveryDateToShopper": {
      "dateFrom": null,
      "dateTo": "2025-09-19T00:00:00Z"
    },
    "deliveryOptionPriceInfo": {
      "price": {
        "retailer": {
          "currency": "EUR",
          "amount": "0.00"
        },
        "shopper": {
          "currency": "USD",
          "amount": "0.00"
        }
      },
      "discounts": []
    },
    "metadataItems": []
  },
  "charges": {
    "totalBeforeTaxesAndCartDiscountsApplied": {
      "retailer": {
        "currency": "EUR",
        "amount": "205.63"
      },
      "shopper": {
        "currency": "USD",
        "amount": "239.98"
      }
    },
    "totalAfterCartDiscount": {
      "retailer": {
        "currency": "EUR",
        "amount": "0.00"
      },
      "shopper": {
        "currency": "USD",
        "amount": "0.00"
      }
    },
    "totalCartDiscount": {
      "retailer": {
        "currency": "EUR",
        "amount": "205.63"
      },
      "shopper": {
        "currency": "USD",
        "amount": "239.98"
      }
    },
    "total": {
      "retailer": {
        "currency": "EUR",
        "amount": "0.00"
      },
      "shopper": {
        "currency": "USD",
        "amount": "0.00"
      }
    },
    "delivery": {
      "retailer": {
        "currency": "EUR",
        "amount": "0.00"
      },
      "shopper": {
        "currency": "USD",
        "amount": "0.00"
      }
    },
    "deliveryDuty": {
      "retailer": {
        "currency": "EUR",
        "amount": "0.00"
      },
      "shopper": {
        "currency": "USD",
        "amount": "0.00"
      }
    },
    "deliveryTaxes": {
      "retailer": {
        "currency": "EUR",
        "amount": "0.00"
      },
      "shopper": {
        "currency": "USD",
        "amount": "0.00"
      }
    },
    "taxes": {
      "retailer": {
        "currency": "EUR",
        "amount": "0.00"
      },
      "shopper": {
        "currency": "USD",
        "amount": "0.00"
      }
    },
    "otherTaxes": {
      "retailer": {
        "currency": "EUR",
        "amount": "0.00"
      },
      "shopper": {
        "currency": "USD",
        "amount": "0.00"
      }
    },
    "administration": {
      "retailer": {
        "currency": "EUR",
        "amount": "0.00"
      },
      "shopper": {
        "currency": "USD",
        "amount": "0.00"
      }
    },
    "duty": {
      "retailer": {
        "currency": "EUR",
        "amount": "0.00"
      },
      "shopper": {
        "currency": "USD",
        "amount": "0.00"
      }
    },
    "uplift": {
      "retailer": {
        "currency": "EUR",
        "amount": "0.00"
      },
      "shopper": {
        "currency": "USD",
        "amount": "0.00"
      }
    }
  },
  "zeroValueOrderCharges": {
    "zeroValueOrderSubTotal": {
      "retailer": {
        "currency": "EUR",
        "amount": "205.63"
      },
      "shopper": {
        "currency": "USD",
        "amount": "239.98"
      }
    },
    "zeroValueOrderTaxes": {
      "retailer": {
        "currency": "EUR",
        "amount": "12.34"
      },
      "shopper": {
        "currency": "USD",
        "amount": "14.40"
      }
    },
    "zeroValueOrderOtherTaxes": {
      "retailer": {
        "currency": "EUR",
        "amount": "0.00"
      },
      "shopper": {
        "currency": "USD",
        "amount": "0.00"
      }
    },
    "zeroValueOrderDuty": {
      "retailer": {
        "currency": "EUR",
        "amount": "0.00"
      },
      "shopper": {
        "currency": "USD",
        "amount": "0.00"
      }
    }
  },
  "contactDetails": [
    {
      "contactDetailType": "IsDelivery",
      "contactDetailsNickName": null,
      "addressId": null,
      "firstName": "Bob",
      "lastName": "American",
      "gender": "None",
      "addressType": null,
      "address1": "4493 Austell Road",
      "address2": "",
      "address3": null,
      "city": "Austell",
      "poBox": null,
      "postalCode": "30106",
      "region": "GA",
      "country": "US",
      "email": "test@unitedstates.com",
      "telephone": "+1 404-413-2000",
      "metadataItems": [],
      "isSelected": true
    },
    {
      "contactDetailType": "IsPayment",
      "contactDetailsNickName": null,
      "addressId": null,
      "firstName": "Bob",
      "lastName": "American",
      "gender": "None",
      "addressType": null,
      "address1": "4493 Austell Road",
      "address2": "",
      "address3": null,
      "city": "Austell",
      "poBox": null,
      "postalCode": "30106",
      "region": "GA",
      "country": "US",
      "email": "test@unitedstates.com",
      "telephone": "+1 404-413-2000",
      "metadataItems": [],
      "isSelected": true
    }
  ],
  "cartType": "ZeroValue"
}
```

{% endcode %}
{% endtab %}

{% tab title="Full discount at cart level" %}
{% code expandable="true" %}

```json
{
  "retailerCartId": "GOC25082115310085US",
  "eShopWorldOrderNumber": "37036749-3c47-4094-9703-859f2a53fb01",
  "checkoutTotal": {
    "retailer": { "currency": "USD", "amount": "0.00" },
    "shopper": { "currency": "USD", "amount": "0.00" }
  },
  "pricingSynchronizationId": null,
  "paymentDetails": {
    "time": "2026-07-01T13:54:30.9257782Z",
    "method": "NoPaymentRequired",
    "methodCardBrand": null,
    "fraudHold": null,
    "amountPaid": null,
    "isOverCounter": null,
    "ticketDetails": null
  },
  "retailerPromoCodes": [],
  "lineItems": [
    {
      "quantity": 1,
      "product": {
        "productCode": "123456789",
        "hsCode": "6211499090",
        "title": "Xbox Wireless Controller",
        "description": "Xbox Wireless Controller",
        "productUnitPriceInfo": {
          "price": {
            "retailer": { "currency": "USD", "amount": "79.99" },
            "shopper": { "currency": "USD", "amount": "79.99" }
          },
          "discounts": []
        },
        "imageUrl": "https://staging.spectrumcustomizer.com/api/assets/generated/recipeset/readable/9XURJSBM/view/north",
        "color": null,
        "size": null,
        "isReturnProhibited": null,
        "metadataItems": [],
        "category": null
      },
      "estimatedDeliveryDate": {
        "fromRetailer": null,
        "fromEShopWorld": "2026-07-01T00:00:00Z",
        "fromEShopWorldRangeFrom": null,
        "fromEShopWorldRangeTo": null
      },
      "lineItemId": 1,
      "charges": {
        "subTotalBeforeTaxesAndCartDiscountsApplied": {
          "retailer": { "currency": "USD", "amount": "79.99" },
          "shopper": { "currency": "USD", "amount": "79.99" }
        },
        "subTotalAfterCartDiscount": {
          "retailer": { "currency": "USD", "amount": "0.00" },
          "shopper": { "currency": "USD", "amount": "0.00" }
        },
        "cartDiscountAttribution": {
          "retailer": { "currency": "USD", "amount": "79.99" },
          "shopper": { "currency": "USD", "amount": "79.99" }
        },
        "subTotal": {
          "retailer": { "currency": "USD", "amount": "0.00" },
          "shopper": { "currency": "USD", "amount": "0.00" }
        },
        "uplift": {
          "retailer": { "currency": "USD", "amount": "0.00" },
          "shopper": { "currency": "USD", "amount": "0.00" }
        },
        "delivery": {
          "retailer": { "currency": "USD", "amount": "0.00" },
          "shopper": { "currency": "USD", "amount": "0.00" }
        },
        "deliveryDuty": {
          "retailer": { "currency": "USD", "amount": "0.00" },
          "shopper": { "currency": "USD", "amount": "0.00" }
        },
        "deliveryTaxes": {
          "retailer": { "currency": "USD", "amount": "0.00" },
          "shopper": { "currency": "USD", "amount": "0.00" }
        },
        "taxes": {
          "retailer": { "currency": "USD", "amount": "0.00" },
          "shopper": { "currency": "USD", "amount": "0.00" }
        },
        "otherTaxes": {
          "retailer": { "currency": "USD", "amount": "0.00" },
          "shopper": { "currency": "USD", "amount": "0.00" }
        },
        "administration": {
          "retailer": { "currency": "USD", "amount": "0.00" },
          "shopper": { "currency": "USD", "amount": "0.00" }
        },
        "duty": {
          "retailer": { "currency": "USD", "amount": "0.00" },
          "shopper": { "currency": "USD", "amount": "0.00" }
        },
        "cashOnDelivery": null,
        "cashOnDeliveryTaxes": null,
        "dutyPromoDiscount": null
      },
      "metadataItems": [],
      "fulfilmentCountryIso": null,
      "deliveryOption": null,
      "articles": null,
      "lineItemZeroValueCharges": {
        "subTotal": {
          "retailer": { "currency": "USD", "amount": "79.99" },
          "shopper": { "currency": "USD", "amount": "79.99" }
        },
        "taxes": {
          "retailer": { "currency": "USD", "amount": "4.80" },
          "shopper": { "currency": "USD", "amount": "4.80" }
        },
        "otherTaxes": {
          "retailer": { "currency": "USD", "amount": "0.00" },
          "shopper": { "currency": "USD", "amount": "0.00" }
        },
        "duty": {
          "retailer": { "currency": "USD", "amount": "0.00" },
          "shopper": { "currency": "USD", "amount": "0.00" }
        }
      },
      "appliedRates": [
        { "chargeConfigurationName": "Vat", "inputPriceName": "Merchandise", "rate": 0.06 }
      ]
    },
    {
      "quantity": 1,
      "product": {
        "productCode": "123456789",
        "hsCode": "6211499090",
        "title": "Xbox Wireless Controller",
        "description": "Xbox Wireless Controller",
        "productUnitPriceInfo": {
          "price": {
            "retailer": { "currency": "USD", "amount": "159.99" },
            "shopper": { "currency": "USD", "amount": "159.99" }
          },
          "discounts": []
        },
        "imageUrl": "https://staging.spectrumcustomizer.com/api/assets/generated/recipeset/readable/9XURJSBM/view/north",
        "color": null,
        "size": null,
        "isReturnProhibited": null,
        "metadataItems": [],
        "category": null
      },
      "estimatedDeliveryDate": {
        "fromRetailer": null,
        "fromEShopWorld": "2026-07-01T00:00:00Z",
        "fromEShopWorldRangeFrom": null,
        "fromEShopWorldRangeTo": null
      },
      "lineItemId": 2,
      "charges": {
        "subTotalBeforeTaxesAndCartDiscountsApplied": {
          "retailer": { "currency": "USD", "amount": "159.99" },
          "shopper": { "currency": "USD", "amount": "159.99" }
        },
        "subTotalAfterCartDiscount": {
          "retailer": { "currency": "USD", "amount": "0.00" },
          "shopper": { "currency": "USD", "amount": "0.00" }
        },
        "cartDiscountAttribution": {
          "retailer": { "currency": "USD", "amount": "159.99" },
          "shopper": { "currency": "USD", "amount": "159.99" }
        },
        "subTotal": {
          "retailer": { "currency": "USD", "amount": "0.00" },
          "shopper": { "currency": "USD", "amount": "0.00" }
        },
        "uplift": {
          "retailer": { "currency": "USD", "amount": "0.00" },
          "shopper": { "currency": "USD", "amount": "0.00" }
        },
        "delivery": {
          "retailer": { "currency": "USD", "amount": "0.00" },
          "shopper": { "currency": "USD", "amount": "0.00" }
        },
        "deliveryDuty": {
          "retailer": { "currency": "USD", "amount": "0.00" },
          "shopper": { "currency": "USD", "amount": "0.00" }
        },
        "deliveryTaxes": {
          "retailer": { "currency": "USD", "amount": "0.00" },
          "shopper": { "currency": "USD", "amount": "0.00" }
        },
        "taxes": {
          "retailer": { "currency": "USD", "amount": "0.00" },
          "shopper": { "currency": "USD", "amount": "0.00" }
        },
        "otherTaxes": {
          "retailer": { "currency": "USD", "amount": "0.00" },
          "shopper": { "currency": "USD", "amount": "0.00" }
        },
        "administration": {
          "retailer": { "currency": "USD", "amount": "0.00" },
          "shopper": { "currency": "USD", "amount": "0.00" }
        },
        "duty": {
          "retailer": { "currency": "USD", "amount": "0.00" },
          "shopper": { "currency": "USD", "amount": "0.00" }
        },
        "cashOnDelivery": null,
        "cashOnDeliveryTaxes": null,
        "dutyPromoDiscount": null
      },
      "metadataItems": [],
      "fulfilmentCountryIso": null,
      "deliveryOption": null,
      "articles": null,
      "lineItemZeroValueCharges": {
        "subTotal": {
          "retailer": { "currency": "USD", "amount": "159.99" },
          "shopper": { "currency": "USD", "amount": "159.99" }
        },
        "taxes": {
          "retailer": { "currency": "USD", "amount": "9.60" },
          "shopper": { "currency": "USD", "amount": "9.60" }
        },
        "otherTaxes": {
          "retailer": { "currency": "USD", "amount": "0.00" },
          "shopper": { "currency": "USD", "amount": "0.00" }
        },
        "duty": {
          "retailer": { "currency": "USD", "amount": "0.00" },
          "shopper": { "currency": "USD", "amount": "0.00" }
        }
      },
      "appliedRates": [
        { "chargeConfigurationName": "Vat", "inputPriceName": "Merchandise", "rate": 0.06 }
      ]
    }
  ],
  "cartDiscountPriceInfo": {
    "price": {
      "retailer": { "currency": "USD", "amount": "0.00" },
      "shopper": { "currency": "USD", "amount": "0.00" }
    },
    "discounts": [
      {
        "title": "PROMOTION",
        "description": "Discount description",
        "discount": {
          "retailer": { "currency": "USD", "amount": "239.98" },
          "shopper": { "currency": "USD", "amount": "239.98" }
        },
        "beforeDiscount": {
          "retailer": { "currency": "USD", "amount": "239.98" },
          "shopper": { "currency": "USD", "amount": "239.98" }
        },
        "percentage": null
      }
    ]
  },
  "deliveryCountryIso": "US",
  "shopperCheckoutExperience": {
    "shopperCultureLanguageIso": "en-IE",
    "emailMarketingOptIn": null,
    "registeredProfileId": null,
    "saveAddressForNextPurchase": false,
    "metadataItems": [],
    "packagingOption": null,
    "smsMarketingOptIn": null,
    "notes": null,
    "phoneMarketingOptIn": null,
    "postMarketingOptIn": null
  },
  "retailerCheckoutExperience": {
    "metadataItems": []
  },
  "deliveryOption": {
    "deliveryOption": "POST",
    "isShipToStore": null,
    "isMultiOrigin": null,
    "isPriceOverrideFromRetailer": true,
    "deliveryOptionPriceInfo": {
      "price": {
        "retailer": { "currency": "USD", "amount": "0.00" },
        "shopper": { "currency": "USD", "amount": "0.00" }
      },
      "discounts": []
    },
    "metadataItems": []
  },
  "retailerDeliveryOption": null,
  "charges": {
    "totalBeforeTaxesAndCartDiscountsApplied": {
      "retailer": { "currency": "USD", "amount": "239.98" },
      "shopper": { "currency": "USD", "amount": "239.98" }
    },
    "totalAfterCartDiscount": {
      "retailer": { "currency": "USD", "amount": "0.00" },
      "shopper": { "currency": "USD", "amount": "0.00" }
    },
    "totalCartDiscount": {
      "retailer": { "currency": "USD", "amount": "239.98" },
      "shopper": { "currency": "USD", "amount": "239.98" }
    },
    "total": {
      "retailer": { "currency": "USD", "amount": "0.00" },
      "shopper": { "currency": "USD", "amount": "0.00" }
    },
    "delivery": {
      "retailer": { "currency": "USD", "amount": "0.00" },
      "shopper": { "currency": "USD", "amount": "0.00" }
    },
    "deliveryDuty": {
      "retailer": { "currency": "USD", "amount": "0.00" },
      "shopper": { "currency": "USD", "amount": "0.00" }
    },
    "deliveryTaxes": {
      "retailer": { "currency": "USD", "amount": "0.00" },
      "shopper": { "currency": "USD", "amount": "0.00" }
    },
    "taxes": {
      "retailer": { "currency": "USD", "amount": "0.00" },
      "shopper": { "currency": "USD", "amount": "0.00" }
    },
    "otherTaxes": {
      "retailer": { "currency": "USD", "amount": "0.00" },
      "shopper": { "currency": "USD", "amount": "0.00" }
    },
    "administration": {
      "retailer": { "currency": "USD", "amount": "0.00" },
      "shopper": { "currency": "USD", "amount": "0.00" }
    },
    "duty": {
      "retailer": { "currency": "USD", "amount": "0.00" },
      "shopper": { "currency": "USD", "amount": "0.00" }
    },
    "uplift": {
      "retailer": { "currency": "USD", "amount": "0.00" },
      "shopper": { "currency": "USD", "amount": "0.00" }
    },
    "cashOnDelivery": null,
    "cashOnDeliveryTaxes": null,
    "dutyPromoDiscount": null
  },
  "zeroValueOrderCharges": {
    "zeroValueOrderSubTotal": {
      "retailer": { "currency": "USD", "amount": "239.98" },
      "shopper": { "currency": "USD", "amount": "239.98" }
    },
    "zeroValueOrderTaxes": {
      "retailer": { "currency": "USD", "amount": "14.40" },
      "shopper": { "currency": "USD", "amount": "14.40" }
    },
    "zeroValueOrderOtherTaxes": {
      "retailer": { "currency": "USD", "amount": "0.00" },
      "shopper": { "currency": "USD", "amount": "0.00" }
    },
    "zeroValueOrderDuty": {
      "retailer": { "currency": "USD", "amount": "0.00" },
      "shopper": { "currency": "USD", "amount": "0.00" }
    }
  },
  "contactDetails": [
    {
      "contactDetailType": "IsDelivery",
      "contactDetailsNickName": null,
      "addressId": null,
      "firstName": "Bxb",
      "lastName": "Axxxxxxn",
      "gender": "None",
      "addressType": null,
      "address1": "4999 Xxxxxxx Xd",
      "address2": null,
      "address3": null,
      "city": "Austell",
      "poBox": null,
      "postalCode": "39999*9998",
      "region": "GA",
      "country": "US",
      "email": "txxx@xxxxxxxxxxxx.xxm",
      "telephone": "+9 999*999*9990",
      "metadataItems": [
        { "name": "is_verified", "value": "true" }
      ],
      "isSelected": true,
      "isDefault": null,
      "saveToProfile": null,
      "status": null,
      "nativeFirstName": null,
      "nativeLastName": null
    },
    {
      "contactDetailType": "IsPayment",
      "contactDetailsNickName": null,
      "addressId": null,
      "firstName": "Bxb",
      "lastName": "Axxxxxxn",
      "gender": "None",
      "addressType": null,
      "address1": "4999 Xxxxxxx Xd",
      "address2": null,
      "address3": null,
      "city": "Austell",
      "poBox": null,
      "postalCode": "39999*9998",
      "region": "GA",
      "country": "US",
      "email": "txxx@xxxxxxxxxxxx.xxm",
      "telephone": "+9 999*999*9990",
      "metadataItems": [
        { "name": "is_verified", "value": "true" }
      ],
      "isSelected": true,
      "isDefault": null,
      "saveToProfile": null,
      "status": null,
      "nativeFirstName": null,
      "nativeLastName": null
    }
  ],
  "paymentRecords": null,
  "cartType": "ZeroValue"
}
```

{% endcode %}
{% endtab %}

{% tab title="Full discount at item level" %}
{% code expandable="true" %}

```json
{
    "retailerCartId": "GOC25567115310085US",
    "eShopWorldOrderNumber": "3dc92160-248f-4218-855d-02371dd08b24",
    "cartType": "ZeroValue",
    "checkoutTotal": {
        "shopper": {
            "currency": "USD",
            "amount": "0.00"
        },
        "retailer": {
            "currency": "EUR",
            "amount": "0.00"
        }
    },
    "pricingSynchronizationId": null,
    "paymentDetails": {
        "time": "2025-08-29T14:57:32.2688803Z",
        "method": "NoPaymentRequired",
        "methodCardBrand": null,
        "fraudHold": false
    },
    "retailerPromoCodes": [],
    "lineItems": [{
            "quantity": 1,
            "product": {
                "productCode": "123456789",
                "hsCode": "6211499090",
                "title": "Xbox Wireless Controller",
                "description": "Xbox Wireless Controller",
                "productUnitPriceInfo": {
                    "price": {
                        "shopper": {
                            "currency": "USD",
                            "amount": "0.00"
                        },
                        "retailer": {
                            "currency": "EUR",
                            "amount": "0.00"
                        }
                    },
                    "discounts": [{
                            "title": null,
                            "description": null,
                            "beforeDiscount": {
                                "shopper": {
                                    "currency": "USD",
                                    "amount": "79.99"
                                },
                                "retailer": {
                                    "currency": "EUR",
                                    "amount": "66.64"
                                }
                            },
                            "discount": {
                                "shopper": {
                                    "currency": "USD",
                                    "amount": "79.99"
                                },
                                "retailer": {
                                    "currency": "EUR",
                                    "amount": "66.64"
                                }
                            }
                        }
                    ]
                },
                "imageUrl": "https://staging.spectrumcustomizer.com/api/assets/generated/recipeset/readable/9XURJSBM/view/north",
                "color": null,
                "size": null,
                "isReturnProhibited": null,
                "metadataItems": []
            },
            "estimatedDeliveryDate": {
                "fromRetailer": "2025-09-19T00:00:00Z",
                "fromEShopWorld": null,
                "fromEShopWorldRangeFrom": null,
                "fromEShopWorldRangeTo": null
            },
            "lineItemId": 1,
            "charges": {
                "subTotalBeforeTaxesAndCartDiscountsApplied": {
                    "shopper": {
                        "currency": "USD",
                        "amount": "0.00"
                    },
                    "retailer": {
                        "currency": "EUR",
                        "amount": "0.00"
                    }
                },
                "subTotalAfterCartDiscount": {
                    "shopper": {
                        "currency": "USD",
                        "amount": "0.00"
                    },
                    "retailer": {
                        "currency": "EUR",
                        "amount": "0.00"
                    }
                },
                "cartDiscountAttribution": {
                    "shopper": {
                        "currency": "USD",
                        "amount": "0.00"
                    },
                    "retailer": {
                        "currency": "EUR",
                        "amount": "0.00"
                    }
                },
                "subTotal": {
                    "shopper": {
                        "currency": "USD",
                        "amount": "0.00"
                    },
                    "retailer": {
                        "currency": "EUR",
                        "amount": "0.00"
                    }
                },
                "uplift": {
                    "shopper": {
                        "currency": "USD",
                        "amount": "0.00"
                    },
                    "retailer": {
                        "currency": "EUR",
                        "amount": "0.00"
                    }
                },
                "delivery": {
                    "shopper": {
                        "currency": "USD",
                        "amount": "0.00"
                    },
                    "retailer": {
                        "currency": "EUR",
                        "amount": "0.00"
                    }
                },
                "deliveryDuty": {
                    "shopper": {
                        "currency": "USD",
                        "amount": "0.00"
                    },
                    "retailer": {
                        "currency": "EUR",
                        "amount": "0.00"
                    }
                },
                "deliveryTaxes": {
                    "shopper": {
                        "currency": "USD",
                        "amount": "0.00"
                    },
                    "retailer": {
                        "currency": "EUR",
                        "amount": "0.00"
                    }
                },
                "taxes": {
                    "shopper": {
                        "currency": "USD",
                        "amount": "0.00"
                    },
                    "retailer": {
                        "currency": "EUR",
                        "amount": "0.00"
                    }
                },
                "otherTaxes": {
                    "shopper": {
                        "currency": "USD",
                        "amount": "0.00"
                    },
                    "retailer": {
                        "currency": "EUR",
                        "amount": "0.00"
                    }
                },
                "administration": {
                    "shopper": {
                        "currency": "USD",
                        "amount": "0.00"
                    },
                    "retailer": {
                        "currency": "EUR",
                        "amount": "0.00"
                    }
                },
                "duty": {
                    "shopper": {
                        "currency": "USD",
                        "amount": "0.00"
                    },
                    "retailer": {
                        "currency": "EUR",
                        "amount": "0.00"
                    }
                }
            },
            "lineItemZeroValueCharges": {
                "subTotal": {
                    "shopper": {
                        "currency": "USD",
                        "amount": "56.33"
                    },
                    "retailer": {
                        "currency": "EUR",
                        "amount": "46.93"
                    }
                },
                "taxes": {
                    "shopper": {
                        "currency": "USD",
                        "amount": "4.80"
                    },
                    "retailer": {
                        "currency": "EUR",
                        "amount": "4.00"
                    }
                },
                "otherTaxes": {
                    "shopper": {
                        "currency": "USD",
                        "amount": "10.90"
                    },
                    "retailer": {
                        "currency": "EUR",
                        "amount": "9.08"
                    }
                },
                "duty": {
                    "shopper": {
                        "currency": "USD",
                        "amount": "23.66"
                    },
                    "retailer": {
                        "currency": "EUR",
                        "amount": "19.71"
                    }
                }
            },
            "metadataItems": []
        }, {
            "quantity": 1,
            "product": {
                "productCode": "123456789",
                "hsCode": "6211499090",
                "title": "Xbox Wireless Controller",
                "description": "SUPER Xbox Wireless Controller SUPER",
                "productUnitPriceInfo": {
                    "price": {
                        "shopper": {
                            "currency": "USD",
                            "amount": "0.00"
                        },
                        "retailer": {
                            "currency": "EUR",
                            "amount": "0.00"
                        }
                    },
                    "discounts": [{
                            "title": null,
                            "description": null,
                            "beforeDiscount": {
                                "shopper": {
                                    "currency": "USD",
                                    "amount": "159.99"
                                },
                                "retailer": {
                                    "currency": "EUR",
                                    "amount": "133.29"
                                }
                            },
                            "discount": {
                                "shopper": {
                                    "currency": "USD",
                                    "amount": "159.99"
                                },
                                "retailer": {
                                    "currency": "EUR",
                                    "amount": "133.29"
                                }
                            }
                        }
                    ]
                },
                "imageUrl": "https://staging.spectrumcustomizer.com/api/assets/generated/recipeset/readable/9XURJSBM/view/north",
                "color": null,
                "size": null,
                "isReturnProhibited": null,
                "metadataItems": []
            },
            "estimatedDeliveryDate": {
                "fromRetailer": "2025-09-19T00:00:00Z",
                "fromEShopWorld": null,
                "fromEShopWorldRangeFrom": null,
                "fromEShopWorldRangeTo": null
            },
            "lineItemId": 2,
            "charges": {
                "subTotalBeforeTaxesAndCartDiscountsApplied": {
                    "shopper": {
                        "currency": "USD",
                        "amount": "0.00"
                    },
                    "retailer": {
                        "currency": "EUR",
                        "amount": "0.00"
                    }
                },
                "subTotalAfterCartDiscount": {
                    "shopper": {
                        "currency": "USD",
                        "amount": "0.00"
                    },
                    "retailer": {
                        "currency": "EUR",
                        "amount": "0.00"
                    }
                },
                "cartDiscountAttribution": {
                    "shopper": {
                        "currency": "USD",
                        "amount": "0.00"
                    },
                    "retailer": {
                        "currency": "EUR",
                        "amount": "0.00"
                    }
                },
                "subTotal": {
                    "shopper": {
                        "currency": "USD",
                        "amount": "0.00"
                    },
                    "retailer": {
                        "currency": "EUR",
                        "amount": "0.00"
                    }
                },
                "uplift": {
                    "shopper": {
                        "currency": "USD",
                        "amount": "0.00"
                    },
                    "retailer": {
                        "currency": "EUR",
                        "amount": "0.00"
                    }
                },
                "delivery": {
                    "shopper": {
                        "currency": "USD",
                        "amount": "0.00"
                    },
                    "retailer": {
                        "currency": "EUR",
                        "amount": "0.00"
                    }
                },
                "deliveryDuty": {
                    "shopper": {
                        "currency": "USD",
                        "amount": "0.00"
                    },
                    "retailer": {
                        "currency": "EUR",
                        "amount": "0.00"
                    }
                },
                "deliveryTaxes": {
                    "shopper": {
                        "currency": "USD",
                        "amount": "0.00"
                    },
                    "retailer": {
                        "currency": "EUR",
                        "amount": "0.00"
                    }
                },
                "taxes": {
                    "shopper": {
                        "currency": "USD",
                        "amount": "0.00"
                    },
                    "retailer": {
                        "currency": "EUR",
                        "amount": "0.00"
                    }
                },
                "otherTaxes": {
                    "shopper": {
                        "currency": "USD",
                        "amount": "0.00"
                    },
                    "retailer": {
                        "currency": "EUR",
                        "amount": "0.00"
                    }
                },
                "administration": {
                    "shopper": {
                        "currency": "USD",
                        "amount": "0.00"
                    },
                    "retailer": {
                        "currency": "EUR",
                        "amount": "0.00"
                    }
                },
                "duty": {
                    "shopper": {
                        "currency": "USD",
                        "amount": "0.00"
                    },
                    "retailer": {
                        "currency": "EUR",
                        "amount": "0.00"
                    }
                }
            },
            "lineItemZeroValueCharges": {
                "subTotal": {
                    "shopper": {
                        "currency": "USD",
                        "amount": "112.67"
                    },
                    "retailer": {
                        "currency": "EUR",
                        "amount": "93.87"
                    }
                },
                "taxes": {
                    "shopper": {
                        "currency": "USD",
                        "amount": "9.60"
                    },
                    "retailer": {
                        "currency": "EUR",
                        "amount": "8.00"
                    }
                },
                "otherTaxes": {
                    "shopper": {
                        "currency": "USD",
                        "amount": "21.81"
                    },
                    "retailer": {
                        "currency": "EUR",
                        "amount": "18.17"
                    }
                },
                "duty": {
                    "shopper": {
                        "currency": "USD",
                        "amount": "47.32"
                    },
                    "retailer": {
                        "currency": "EUR",
                        "amount": "39.42"
                    }
                }
            },
            "metadataItems": []
        }
    ],
    "cartDiscountPriceInfo": null,
    "deliveryCountryIso": "US",
    "shopperCheckoutExperience": {
        "shopperCultureLanguageIso": "en-IE",
        "emailMarketingOptIn": null,
        "registeredProfileId": null,
        "saveAddressForNextPurchase": false,
        "metadataItems": []
    },
    "retailerCheckoutExperience": {
        "metadataItems": []
    },
    "deliveryOption": null,
    "retailerDeliveryOption": {
        "deliveryOption": "POST",
        "title": "Standard",
        "estimatedDeliveryDateToShopper": {
            "dateFrom": null,
            "dateTo": "2025-09-19T00:00:00Z"
        },
        "deliveryOptionPriceInfo": {
            "price": {
                "shopper": {
                    "currency": "USD",
                    "amount": "0.00"
                },
                "retailer": {
                    "currency": "EUR",
                    "amount": "0.00"
                }
            },
            "discounts": []
        },
        "metadataItems": []
    },
    "charges": {
        "totalBeforeTaxesAndCartDiscountsApplied": {
            "shopper": {
                "currency": "USD",
                "amount": "0.00"
            },
            "retailer": {
                "currency": "EUR",
                "amount": "0.00"
            }
        },
        "totalAfterCartDiscount": {
            "shopper": {
                "currency": "USD",
                "amount": "0.00"
            },
            "retailer": {
                "currency": "EUR",
                "amount": "0.00"
            }
        },
        "totalCartDiscount": {
            "shopper": {
                "currency": "USD",
                "amount": "0.00"
            },
            "retailer": {
                "currency": "EUR",
                "amount": "0.00"
            }
        },
        "total": {
            "shopper": {
                "currency": "USD",
                "amount": "0.00"
            },
            "retailer": {
                "currency": "EUR",
                "amount": "0.00"
            }
        },
        "delivery": {
            "shopper": {
                "currency": "USD",
                "amount": "0.00"
            },
            "retailer": {
                "currency": "EUR",
                "amount": "0.00"
            }
        },
        "deliveryDuty": {
            "shopper": {
                "currency": "USD",
                "amount": "0.00"
            },
            "retailer": {
                "currency": "EUR",
                "amount": "0.00"
            }
        },
        "deliveryTaxes": {
            "shopper": {
                "currency": "USD",
                "amount": "0.00"
            },
            "retailer": {
                "currency": "EUR",
                "amount": "0.00"
            }
        },
        "taxes": {
            "shopper": {
                "currency": "USD",
                "amount": "0.00"
            },
            "retailer": {
                "currency": "EUR",
                "amount": "0.00"
            }
        },
        "otherTaxes": {
            "shopper": {
                "currency": "USD",
                "amount": "0.00"
            },
            "retailer": {
                "currency": "EUR",
                "amount": "0.00"
            }
        },
        "administration": {
            "shopper": {
                "currency": "USD",
                "amount": "0.00"
            },
            "retailer": {
                "currency": "EUR",
                "amount": "0.00"
            }
        },
        "duty": {
            "shopper": {
                "currency": "USD",
                "amount": "0.00"
            },
            "retailer": {
                "currency": "EUR",
                "amount": "0.00"
            }
        },
        "uplift": {
            "shopper": {
                "currency": "USD",
                "amount": "0.00"
            },
            "retailer": {
                "currency": "EUR",
                "amount": "0.00"
            }
        }
    },
    "zeroValueOrderCharges": {
        "zeroValueOrderSubTotal": {
            "shopper": {
                "currency": "USD",
                "amount": "169.00"
            },
            "retailer": {
                "currency": "EUR",
                "amount": "140.80"
            }
        },
        "zeroValueOrderTaxes": {
            "shopper": {
                "currency": "USD",
                "amount": "14.40"
            },
            "retailer": {
                "currency": "EUR",
                "amount": "12.00"
            }
        },
        "zeroValueOrderOtherTaxes": {
            "shopper": {
                "currency": "USD",
                "amount": "32.71"
            },
            "retailer": {
                "currency": "EUR",
                "amount": "27.25"
            }
        },
        "zeroValueOrderDuty": {
            "shopper": {
                "currency": "USD",
                "amount": "70.98"
            },
            "retailer": {
                "currency": "EUR",
                "amount": "59.13"
            }
        }
    },
    "contactDetails": [{
            "contactDetailType": "IsDelivery",
            "contactDetailsNickName": null,
            "addressId": null,
            "firstName": "Bob",
            "lastName": "American",
            "gender": "None",
            "address1": "4493 Austell Road",
            "address2": "",
            "address3": null,
            "city": "Austell",
            "poBox": null,
            "postalCode": "30106",
            "region": "GA",
            "country": "US",
            "email": "test@unitedstates.com",
            "telephone": "+1 404-413-2000",
            "metadataItems": [],
            "isSelected": true
        }, {
            "contactDetailType": "IsPayment",
            "contactDetailsNickName": null,
            "addressId": null,
            "firstName": "Bob",
            "lastName": "American",
            "gender": "None",
            "address1": "4493 Austell Road",
            "address2": "",
            "address3": null,
            "city": "Austell",
            "poBox": null,
            "postalCode": "30106",
            "region": "GA",
            "country": "US",
            "email": "test@unitedstates.com",
            "telephone": "+1 404-413-2000",
            "metadataItems": [],
            "isSelected": true
        }
    ],
    "paymentRecords": [{
            "time": "2025-08-29T14:57:32.2688803Z",
            "method": "NoPaymentRequired",
            "methodCardBrand": null,
            "fraudHold": false
        }
    ]
}
```

{% endcode %}
{% endtab %}
{% endtabs %}
