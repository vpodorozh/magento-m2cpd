### Public content
https://devdocs.magento.com/guides/v2.2/extension-dev-guide/cache/page-caching/public-content.html

#### How does it work: 
1. [M2] generate page and insert "esi" tags instead of blocks that has TTL (check \Magento\PageCache\Observer\ProcessLayoutRenderElement::execute) 
2. [Varnish] process "esi" tags by source urls and insert content from source urls into page 
3. [End user] get page from Varnish 

#### When FPC works:
FPC is Enabled && Current route is cacheable (check below) && Varnish is enabled.

#### When block be retrieved using ESI (M2 FPC):
FPC works (prev point) && Block has TTL 

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

------------------------

#### FPC is NOT a `private content`:
1. Only public content is cached using FPC. Any user related data is cached using private content.
2. FPC stores cache on server and generate page on server using Varnish. Private content use AJAX calls to get needed data and store cache on local storage in browser.