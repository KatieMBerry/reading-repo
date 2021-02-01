## Intro to Webpack 
### https://www.freecodecamp.org/news/an-intro-to-webpack-what-it-is-and-how-to-use-it-8304ecdc3c60/
### https://github.com/sirdarthvader/webpack-react-setup

- webpack - goes through your package and creates dependency graph that consists of modules
  - condenses the whole into a new smaller package/single bundle.js file
  - can be plugged into an html file 
- webpack came about b/c with just van JS, html and css there was a need for new libraries and frameworks
  - design pattersn also emerged (ie js modules/chunks of smaller code that do9es one thing)
  - polyfills = helper code that helps browsers interpret code (can be used for older browsers for Es6, etc)
- React.js = UI library for complex UIs that uses ES6 classes and import statements
- create-react-app = CLI tool for bootstrapping boilerplate dev setup

to setup webpack:
1. npm init (need newest node.js and npm first) //creates starter package json that houses dependencies
2. npm i react  react-dom --save //creates simple react app)
3. npm i webpack webpack-dev-server webpack-cli --save --dev (specifies these modules are just dependencies)//webpack to bundle app
  - 'hot reloading' = comes with webpack dev server
4. npm i babel-core babel-loader //need tool like babel so react classes & imp statements are readable by all browsers
   @babel/preset-react @babel/preset-env
   html-webpack-plugin --save --dev //works with react and ES2015 Es6 code
5. webpack.config.js at root of app
  - requires default path module to access file location
  requires htmlwebpackplugin to generate html filefor serving bundled js files
  - entry prop = specifies which file webpack should start with to get dependency graph created
  - output prop = says where bundled file should be madeand it's name (output.path & output.filename)
  - loaders = says what webpack should do with each type of file
6. .babelrc file = uses babel preset for ES6 criteria
7. add react code to index.js file and import react and react-dom
8. app.js
9. enable hot reloading = every time a change is detected, browser reloads page; will build and bundle app
10. npm build //bundles app and ready to be deployed

## webpack concepts
### https://webpack.js.org/concepts/

- wp = static module bundler for JS apps; internally builds dependency graph (maps every module and makes bundle)
    - very configurable to fit needs
- entry point = says which module wp should use to begin building dep graph
  - default = ./src/index.js
  - can specify other or multiple entry pts by setting entry prop in webpack.config.js
- output prop = tells where to emit bundles and how to name them
  - default = ./dist/main.js(main output)
- loaders = allow wp to process other types of files and converts to readable modules to add to dep graph
- plugins = can be used to perform wide range of tasks(bundle optimization, asset management, etc.)
- mode = dev, production, none

## React: Rendering Elements
### https://reactjs.org/docs/rendering-elements.html
- element = describes what want to see on screen 
  - in react, eles are objects and cheap to use 
  - immutable = like a single frame in movie reel/ui at a point in time
  - react-dom updates dom
- apps built w/ just react usually have single root dom node (everything inside is managed by react dom)
- to update the rendered ele, need to create new ele and padd thru reactdom.render)
  - only updates what is necessary
  
  ## Intro to JSX
  ### https://reactjs.org/docs/introducing-jsx.html
  = syntax extension of JS
  - describes what UI should look like with react
  - produces react elements
  - more usefule error messages with JSX
  - After compilation, JSX expressions become regular JavaScript function calls and evaluate to JavaScript objects
