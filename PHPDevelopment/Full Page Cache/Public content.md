### Public content
https://devdocs.magento.com/guides/v2.2/extension-dev-guide/cache/page-caching/public-content.html


#### Not cacheable route:
1. Has 'cachable="false"' block in layout.
2. Receive POST or PUT HTTP requests.
3. Uses not cacheable HTTP headers (e.g. 'Cache-Control', 'no-store, no-cache, must-revalidate, max-age=0')

#### Cacheable route:
1. Receive GET or HEAD HTTP requests.
2. Has no one 'cachable="false"' block in layout.

#### Add personal Full Page Cache content variosity
1. Create plugin for \Magento\Framework\App\Http\Context.
2. Intercept 'getVaryString' and add your personal context value.
3. Full page cache will be different for the same page based on your context value.

#### Block & Model identity
1. Both implements \Magento\Framework\DataObject\IdentityInterface
2. Have cache tags, which could depends on model identity.
3. After model changing, invalidate corresponding (by identity) block.

