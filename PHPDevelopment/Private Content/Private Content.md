### Private Content
https://devdocs.magento.com/guides/v2.2/extension-dev-guide/cache/page-caching/private-content.html

1. Should not be cacheable.
2. Stores in browser.
3. Use Magento 'customer data' JS library.
4. To get private content in js component - use "customer-data" component, it contain all private content and manage it.

#### General info

##### PC && Knokout - where data is taken and how is it processed
[Browser side]
1. Add product to the cart
2. JS in browser invalidate PC
3. JS send request to Magento to get new PC
4. JS bind data from new PC request to binded variables for knokout
5. Knoknout get data from bind vars and publish them on HTML

["customer-data"] - data hub on frontend, it stores all PC sections data and handles its update from server

##### Private content - main logic 
All content that is depend on browser cookie, local storage and client actions (add to cart) - is private content.

##### How the data is taken from backend to frontend 
Two ways:
1. XHR requests to get data via Magento API, that is initiated by frontend js models
2. Data that is stored into js vars in phtml template – some kind of predefined data

##### Main Frontend Magento Architecture
M2 frontened uses MVVM architecture.
* Knokout templates and core - data view // M1 example: template and layout
* JS view models // M1 example: Controller and Blocks
* JS Models - data handling and processing //  M1 example: Models

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