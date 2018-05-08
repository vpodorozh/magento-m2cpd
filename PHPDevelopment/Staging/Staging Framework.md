### Staging
https://devdocs.magento.com/guides/v2.2/extension-dev-guide/staging.html

Allow to create and manage scheduled campaigns and store updates. Allow preview for future campaign.

#### Modules:
1. Magento_Staging
    1. Staging Framework
    2. Staging Dashboard in Adminhtml
    3. API
    4. Preview Mode
2. Magento_BundleStaging
    1. Allow schedule updates for bundle products
    2. All bundle options of the product which going to be scheduled, could be edited
3. Magento_CatalogImportExportStaging
    1. adds a plugin on Magento\CatalogImportExport\Model\Import\Product::saveProductEntity to add version and sequence information to the product entity
    2.  listens to the **catalog_product_import_bunch_delete_commit_before** event to delete values from the sequence table when products are being deleted
4. Magento_CatalogInventoryStaging
    1. Adds the disabled “Stock Status” field on the Schedule Update form of a product during form rendering.
5. Magento_CatalogRuleStaging
    1. Make Magento_CatalogRule compatible with Staging
    2. Allow scheduling Catalog Rules in Staging
6. Magento_CatalogStaging
    1. Main module for catalog, products which make them compatible with Staging
    2. Catalog-Product relation and Category URL can not be changed in Staging
    3. Product Qty, Url key and SKU can not be changed in Staging
7. Magento_CatalogUrlRewriteStaging
    1. Technical module
    2. Disable opportunity to change URL for product or category
8. Magento_CheckoutStaging
    1. Provide opportunity to use preview mode
    2. Creates demo quotes and disable order creation
    3. Remove old demo quotes
9. Magento_CmsStaging
    1. Allow staging of CMS Blocks/Pages
    2. URL key can be  changed in Staging
10. Magento_ConfigurableProductStaging
    1. Add 'Configurations' tab and configuration wizard to Schedule Update form
11. Magento_DownloadableStaging
    1. Make Downloadable products compatible with Staging
    2. Add “Downloadable information” to product form
12. Magento_GiftCardStaging
    1. Add Gift Card Product attributes to the Staging
13. Magento_GiftMessageStaging
    1. Enables you to stage the “Allow Gift Message” flag in the “Gift Options” field set in the “Schedule Update” form of the product.
14. Magento_GiftWrappingStaging
    1. Enable/disable gift wrapping (“Allow Gift Wrapping” field)
    2. Set a price for the gift wrapping (“Price for Gift Wrapping” field).
15. Magento_GoogleOptimizerStaging
    1. Enable to stage parameters added by the Magento_GoogleOptimizer in the Search Optimization field set.
16. Magento_GroupedProductStaging
    1. Allow stage products, assigned to grouped product
17. Magento_LayeredNavigationStaging
    1. Disables the Magento_LayeredNavigation module functionality in the staging preview mode. 
18. Magento_MsrpStaging
    1. Add to Advanced Pricing form Manufacturer’s **Suggested Retail Price** and **Display Actual Price**
19. Magento_PaymentStaging
    1. Show offline payment methods in staging preview mode
20. Magento_ProductVideoStaging
    1. Allow add video in staging mode
21. Magento_ReviewStaging
    1. Add product review list to product staging form
    2. You cannot create an update for a product review.
22. Magento_RmaStaging
    1. Adds the Autosettings field set to the Schedule update form of a product.
23. Magento_SalesRuleStaging
    1. Changes the Cart Price Rules page and the sales rule related database tables to make them compatible with the Magento Staging Framework
24. Magento_SearchStaging
    1. Adds Search to the staging preview but disables the searching functionality.
25. Magento_WeeeStaging
    1. It adds an opportunity to schedule a Fixed Product Tax type attribute using the Schedule Update form of a product.