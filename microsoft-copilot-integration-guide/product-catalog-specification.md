---
description: Field requirements for product catalog CSV files.
---

# Product catalog specification

Use this specification when preparing catalog files.&#x20;

{% file src="../.gitbook/assets/{catalogFileName}-{countryIso3166Alpha2}-template.csv" %}

### Core fields

| Field                | Requirement | Description and example                                                                                    |
| -------------------- | ----------- | ---------------------------------------------------------------------------------------------------------- |
| `productId`          | Required    | Unique retailer product ID or SKU. Maximum 50 characters. Example: `SKU-12345`.                            |
| `marketCountryIso`   | Optional    | Two-letter ISO 3166-1 market code. Required on every row for multi-country files. Example: `GB`.           |
| `title`              | Required    | Product title. Example: `Men’s Cotton Oxford Shirt`.                                                       |
| `brand`              | Optional    | Manufacturer, brand, or publisher. Maximum 70 characters and 10 words. Defaults to retailer brand.         |
| `mpn`                | Optional    | Manufacturer Part Number. Up to 70 alphanumeric characters.                                                |
| `gtin`               | Recommended | Barcode, GTIN, UPC, EAN, or ISBN. Numeric, up to 14 digits per value. Separate up to 10 values with pipes. |
| `description`        | Required    | No HTML or promotional text. Maximum 10,000 characters. Include size, colour, and pattern where relevant.  |
| `material`           | Optional    | Material composition. Required unless the item is a digital good. Example: `100% Cotton`.                  |
| `countryOfOriginIso` | Required    | Two-letter ISO 3166-1 manufacturing country code.                                                          |
| `availability`       | Required    | One of: `preorder`, `out_of_stock`, `in_stock`, or `backorder`.                                            |
| `condition`          | Optional    | One of: `new`, `refurbished`, or `used`.                                                                   |
| `contentLanguageISO` | Optional    | Two-letter ISO 639-1 product language code. Example: `en`.                                                 |

### Price, weight, and links

| Field                  | Requirement | Description and example                                     |
| ---------------------- | ----------- | ----------------------------------------------------------- |
| `price`                | Required    | Decimal price with a full-stop separator. Example: `29.99`. |
| `currencyIso`          | Required    | ISO 4217 currency code. Example: `GBP`.                     |
| `weight`               | Optional    | Decimal product weight. Example: `0.35`.                    |
| `weightUnit`           | Optional    | One of: `lb`, `oz`, `g`, or `kg`.                           |
| `link`                 | Required    | Direct product page URL.                                    |
| `imageLink`            | Required    | Main product image URL.                                     |
| `additionalImageLinks` | Optional    | Up to 10 extra image URLs, separated by commas.             |

### Product attributes

| Field         | Requirement | Description and example                                                                  |
| ------------- | ----------- | ---------------------------------------------------------------------------------------- |
| `color`       | Conditional | Up to three values separated by `/`, dominant first. Required for Apparel & Accessories. |
| `size`        | Optional    | Product size. Maximum 100 characters.                                                    |
| `gender`      | Optional    | One of: `male`, `female`, or `unisex`.                                                   |
| `category`    | Optional    | Category path using `>` only. Maximum 255 characters.                                    |
| `productType` | Optional    | Full category path. Maximum 750 characters.                                              |
| `pattern`     | Optional    | Pattern or graphic print. Maximum 100 characters.                                        |
| `keywords`    | Recommended | Highlights and USPs. Maximum 150 characters. Separate values with commas.                |
| `ageGroup`    | Conditional | `newborn`, `infant`, `toddler`, `kids`, or `adult`. Required for Apparel.                |
| `itemGroupId` | Optional    | Shared ID for variants. Up to 50 alphanumeric characters.                                |
| `sizeType`    | Optional    | Apparel modifier. Example: `petite`.                                                     |
| `sizeSystem`  | Optional    | Apparel modifier. Example: `UK`.                                                         |

### Promotions and bundles

| Field                    | Requirement | Description and example                                        |
| ------------------------ | ----------- | -------------------------------------------------------------- |
| `salePrice`              | Optional    | Discounted item price. Example: `21.99`.                       |
| `salePriceEffectiveDate` | Optional    | Sale time range. Example: `2026-06-25T00:00/2026-06-30T23:59`. |
| `costOfGoodsSold`        | Optional    | Merchant’s actual item cost. Example: `15.00`.                 |
| `promotionId`            | Optional    | Promotion identifier. Example: `SUMMER_SALE`.                  |
| `isBundle`               | Conditional | Merchant-defined bundle flag: `yes` or `no`.                   |
| `multipack`              | Conditional | Number of identical grouped items. Example: `3`.               |
| `adult`                  | Conditional | Adult-oriented content flag: `yes` or `no`.                    |

### Enrichment and shopper information

| Field                    | Requirement | Description and example                                                                                |
| ------------------------ | ----------- | ------------------------------------------------------------------------------------------------------ |
| `productHighlight`       | Optional    | Product highlights, separated by commas.                                                               |
| `productDetail`          | Optional    | Product details using structured key-value information.                                                |
| `returnExceptionPolicy`  | Optional    | Product-specific return exception. Maximum 50 characters. This information may appear during checkout. |
| `consumerMessageType`    | Optional    | Warning category, such as `legal_disclaimer`, `safety_warning`, or `prop_65`.                          |
| `consumerMessageContent` | Optional    | Shopper warning text. Maximum 1,000 characters. Supports `<b>`, `<br>`, `<i>`, and `<a href>`.         |
| `documentLinks`          | Optional    | Related manual, assembly, or safety document links. Separate values with commas.                       |
| `relatedProducts`        | Optional    | Related products and their relationship identifiers. Separate values with commas.                      |

### GTIN formats

Use numeric GTIN values only. Supported formats include:

* **UPC / GTIN-12 / UPC-A** — 12 digits, mainly North America.
* **EAN / GTIN-13** — usually 13 digits, also 8 or 14 digits.
* **JAN / GTIN-13** — 8 or 13 digits, used in Japan.
* **ISBN** — 10 or 13 digits for books. ISBN-13 usually starts with `978` or `979`.
