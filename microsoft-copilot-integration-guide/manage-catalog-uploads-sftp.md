---
description: Upload and maintain market-specific product catalogs through SFTP.
---

# Manage catalog uploads (SFTP)

Send catalog files to ESW through SFTP. Use one file per market whenever prices or availability change.

### Upload cadence

* Send an initial full catalog with every active, in-stock product.
* Upload a new file for price, availability, or attribute changes.
* Upload a full catalog at least monthly.

Set `availability` to `out_of_stock` to remove a product. A file can contain new products, updates, and removals.

Allow up to 72 hours after the first successful upload for Microsoft validation. ESW monitors validation and resolves blockers to product visibility.

### SFTP location

Upload files to:

```hurl
https://eshopworld3.files.com/files/Development/Core/Retailers/<BRANDCODE>RetailersFTP/<ENV>/ProductFeed/Pending
```

* `<BRANDCODE>` is your agreed brand code.
* `<ENV>` is the target environment, such as `TEST` or `PROD`.

Example:

```hurl
https://eshopworld3.files.com/files/Development/Core/Retailers/PGLRetailersFTP/TEST/ProductFeed/Pending
```

### File naming

Use this filename format:

```csv
{catalogFileName}-{countryIso3166Alpha2}.csv
```

### Preserve product IDs in Excel

Excel can convert long values into scientific notation. This can corrupt GTINs, product IDs, and MPNs.

1. Format every ID column as **Text** before entering values.
2. Import CSV files with **Data → From Text/CSV**.
3. Set the GTIN column type to **Text** before loading.

Before upload, confirm that each ID is complete. For example, use `5063589815347`, not `1.24504323E+12`.

Open the CSV as a `.txt` file in Notepad to verify IDs. Reformatting a converted Excel cell does not restore its original value. Correct the source data and export again.
