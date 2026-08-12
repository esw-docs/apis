# Shipping Override

Applies specific shipping rates for promotions — either through ESW-fulfilled delivery options or retailer-fulfilled ones.

Use `deliveryOptions[]` to override an ESW delivery option. Use `retailerDeliveryOptions[]` when the retailer fulfills delivery. Each option can define its displayed price and delivery estimate, helping promotions present the intended shipping offer at checkout.

| Field                                                       | Type                                    | Description                                                                           |
| ----------------------------------------------------------- | --------------------------------------- | ------------------------------------------------------------------------------------- |
| `deliveryOptions[].deliveryOption`                          | string, max 15                          | Required. Preferred delivery option code (e.g. `Post`, `Exp2`), as agreed with ESW.   |
| `deliveryOptions[].deliveryOptionOverridePriceInfo`         | `PreOrderPriceInfoRequestDto`           | Overrides the price for this delivery option, optionally with fixed-amount discounts. |
| `deliveryOptions[].estimatedDeliveryDateOverride`           | date-time                               | Overrides the estimated delivery date shown to the shopper.                           |
| `retailerDeliveryOptions[].deliveryOption`                  | string                                  | Required. Internal ESW identifier for the selected option.                            |
| `retailerDeliveryOptions[].title`                           | string, max 30                          | Required. Title of the non-ESW delivery option shown to the shopper.                  |
| `retailerDeliveryOptions[].estimatedDeliveryDateToShopper`  | `PreOrderEstimatedDeliveryDateRangeDto` | Required. `dateTo` is mandatory; `dateFrom` is optional to show a range.              |
| `retailerDeliveryOptions[].retailerDeliveryOptionPriceInfo` | `PreOrderPriceInfoRequestDto`           | Required. Price for the retailer-fulfilled option.                                    |
