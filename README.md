The target website loads its content dynamically using JavaScript. When accessing the page through the requests library, the returned HTML does not contain the quote text or 
author names. This shows that the required data is not included in the initial server response. Since requests only retrieves static HTML and does not execute JavaScript, it 
cannot extract dynamically rendered content. Therefore, using requests + BeautifulSoup fails for this website.
The page source does not display the quotes, but the quotes are visible in the browser’s rendered DOM after the page loads. This difference indicates that the content is injected 
into the page after JavaScript execution. Additionally, no publicly accessible JSON API endpoint was identified that could be used to directly retrieve the quote data. This 
confirms that the website relies on client-side rendering rather than serving structured data through an API.
Because the data is generated dynamically and not available in the raw HTML response, static scraping methods are not suitable. For this reason, Selenium was selected as the
scraping method. Selenium launches a real browser session, executes JavaScript, waits for the page to fully render, and allows access to the dynamically loaded elements. 
Therefore, Selenium is the correct and technically appropriate approach for extracting data from this website.
