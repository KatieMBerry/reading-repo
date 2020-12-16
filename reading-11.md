## Web Scraping
- can use REGEX on html string, but not flexible and can be confusing; may contain unwanted items
- html parsers: 
  1. Cheerio: uses JQUERY api
      - downside is it doesn't execute JS
  2. JS DOM - can maintain the DOM
  3. Pupeteer: browser automation library
       - similar to a user interacting with browser
       - can produce screenshots and pdfs of pages
       - automates user interactions and can also be used in testing UI
  4. Nightmare: browser automation library
       - similar to user interacting with browser
    
## Ele = Doc.QuerySelector(Selector)
- returns the first element within the doc that matches the selector, or null
- uses pre-order traversal
- use escape with forward slash if not using standard css sybtax or twice if using a literal string

## Ele = Doc.QuerySelectorAll()
- returns element list/node list containing one element object for each element that matches the selector, or an empty nodelist
  - can treat nodelist as array and use array notation to access 
