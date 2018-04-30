### Private Content
https://devdocs.magento.com/guides/v2.2/extension-dev-guide/cache/page-caching/private-content.html

1. Should not be cacheable.
2. Stores in browser.
3. Use Magento 'customer data' JS library.

#### Section source
##### Load private data
1. Create your source with implementing Magento\Customer\CustomerData\SectionSourceInterface.
2. Inject source via di.xml to Magento\Customer\CustomerData\SectionPoolInterface

##### Invalidate data
1. Declare route when your data will be invalidated in sections.xml
2. Routes should works with POST requests.
3. Could be invalidated via JS.

#### Use templates and KO
1. Create your template.
2. Replace private content data with KO placeholders.
3. Retrieve and describe behaviour of your data in UI component.