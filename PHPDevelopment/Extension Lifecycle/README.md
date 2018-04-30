### Install Scripts
https://devdocs.magento.com/guides/v2.2/extension-dev-guide/prepare/lifecycle.html

1. Schema 
    - Install Schema - \Magento\Framework\Setup\InstallSchemaInterface
    - Upgrade Schema - \Magento\Framework\Setup\UpgradeSchemaInterface
    - Recurring Schema - Recurring implements \Magento\Framework\Setup\InstallSchemaInterface
2. Data
    - Install Data - \Magento\Framework\Setup\InstallDataInterface
    - Upgrade Data - \Magento\Framework\Setup\UpgradeDataInterface
    - Recurring Data - RecurringData implements \Magento\Framework\Setup\InstallDataInterface
3. Uninstall - \Magento\Framework\Setup\UninstallInterface
    - execute by composer when remove module
    - bin/magento module:uninstall --remove-data <module_name>
4. Arguments
    - Database interface - ModuleDataSetupInterface
    - Module version - ModuleContextInterface