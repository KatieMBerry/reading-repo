## Express Routing
- how app endpoints respond to client requests
- app listens for requests to endpoints and calls related callback functions
  - more than one callback function can handle a route, using next()
    - can use an array of cb functions
- chaining routes for modularity with app.route()
- express.router() - mountable route handlers 
  - mounts router on path of main app (/birds and /birds/about)

## Supertest
- can be used with any or no test frameworks

## Express Middleware
- functions with access to req and res objects and next()
  - can modify req/res
  - can end rew/res cycle
  - calls next() to pass control to following middleware function
    - to skip remaining middleware functions, call nect('router')
- built-in: express.static, .json, .urlencoded
- 3rd party: body-parser (parses body of requests)
