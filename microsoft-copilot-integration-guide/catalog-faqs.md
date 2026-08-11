---
description: Resolve common catalog upload and product discovery questions.
---

# Catalog FAQs

### Uploading catalogs

<details>

<summary>Where do I upload my catalog?</summary>

Upload to your assigned tenant folder through SFTP. Use the exact brand code, environment, and `ProductFeed/Pending` path provided by ESW. Confirm the folder with your ESW Customer Success Manager if needed.

</details>

<details>

<summary>Can I upload multiple files for one market?</summary>

No. Send one CSV per market. Include every product for that market. Do not split files by category, brand, or action type.

</details>

<details>

<summary>What belongs in my first upload?</summary>

Include every active, in-stock product you want discoverable in Microsoft Copilot. Include required fields and useful selling points, features, category, material, and intended use.

</details>

<details>

<summary>What format do I need?</summary>

Send a UTF-8 CSV. Populate mandatory fields for each product category. Validate the file before upload.

</details>

### Timing and markets

<details>

<summary>When do products appear in Microsoft Merchant Center and Copilot?</summary>

Allow up to 72 hours after successful upload. Upload at least four days before launches, campaigns, or price changes.

</details>

<details>

<summary>Which markets support Microsoft Copilot purchases?</summary>

Microsoft Copilot purchasing currently supports the United States. Prioritize accurate US catalogs, then prepare market-specific files for future expansion.

</details>

<details>

<summary>When should I upload sale prices?</summary>

Upload changes at least 72 hours before launch. Upload major event changes at least four days ahead. Verify results before peak traffic.

</details>

<details>

<summary>How often should I update catalogs?</summary>

Send a full catalog at least monthly. Upload price, availability, and removal changes as soon as they occur.

</details>

### Errors and corrections

<details>

<summary>Why was my entire file rejected?</summary>

A structural error prevented parsing. Export a fresh UTF-8 CSV. Confirm equal column counts, escaped commas and quotes, then re-upload.

</details>

<details>

<summary>Can some products succeed while others fail?</summary>

Yes, if the file structure is valid. ESW uploads valid products and logs failed products. Correct failed SKUs and re-upload them.

</details>

<details>

<summary>Why did products fail with a non-USD pricing error?</summary>

Microsoft Copilot purchasing currently requires USD. Convert prices to USD, remove currency symbols, use values like `49.99`, then re-upload.

</details>

<details>

<summary>How do I update or remove products?</summary>

Use the same SKU or product ID and upload the latest values. To remove a product, set `availability` to `out_of_stock`. Omitting a SKU does not remove it.

</details>

<details>

<summary>Why are IDs displayed as scientific notation?</summary>

Excel converted long IDs and corrupted them. Regenerate the CSV from the source system. Import with **Data → From Text/CSV** and set ID columns to **Text**.

</details>

<details>

<summary>How do I verify data before uploading?</summary>

Open the CSV in Notepad. Confirm long IDs appear in full, such as `5063589815347`, not `1.23E+13`. Regenerate the file if values are converted.

</details>

<details>

<summary>What does an empty catalog file error mean?</summary>

The CSV has no product rows. Re-run the export. Confirm it has headers and product data, then upload it again.

</details>

<details>

<summary>Why are products missing mandatory fields?</summary>

Each category requires specific fields. Use the catalog specification, populate required fields, and re-upload corrected products.

</details>
