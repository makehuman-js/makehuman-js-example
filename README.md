# makehuman-js example ui

Example web app using [makehuman-js](https://github.com/makehuman-js/makehuman-js)

Live version at [makehuman-js-example.wassname.com](http://makehuman-js-example.wassname.com/) (NSFW while loading)

![](docs/screenshot.png)

## Install and run

- clone the repository
- run `npm install`
- run `npm start`
- open http://localhost:8080 in the browser


## Development environment

If you want to edit makehuman-js and makehuman-data as well you will want to set up a development environment with "npm link" and `webpack --watch`:

- clone this repo, makehuman-js, and makehuman-data into three seperate folders: "makehuman-js-example", "makehuman-js" and "makehuman-data"
- in the makehuman-data folder:
  - register makehuman-data using the command [`npm link`](https://medium.com/@alexishevia/the-magic-behind-npm-link-d94dcb3a81af).  This way imports will use your local code (read more [here](http://justjs.com/posts/npm-link-developing-your-own-npm-modules-without-tears)).
- in the makehuman-js folder:
  - run `npm link`
  - install dev dependancies with `npm install --dev`
  - open a seperate terminal, go to this folder, and run `npm run watch`. This will have [webpack watch](https://webpack.js.org/configuration/watch/) for changes to the source code (such as human.js) and if it sees any it will regerate makehuman.js. Leave this running while you develop.
  - If you get "webpack not found" or similar, while running the previous step you may also need to install webpack globally to make the command available in the terminal: `npm install -g webpack@2.1.0`.
- in the makehuman-js-example folder 
  - install dependencies with `npm install`
  - run `npm link makehuman-js` and `npm link makehuman-data`
  - run `npm start`
- open http://localhost:8080 in the browser

Now if you change a source file in makehuman-js you will see the change reflected in the web app, that means it's working.

Why do it this way? You could also refactor makehuman-js-example to be a webpack app which would simplify the development process but would complicate the example. I chose a simpler example.
