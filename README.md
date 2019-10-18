# Create a basic React app without the create-react-app build setup

## Create package.json file
mkdir react-app && cd react-app
npm init -y

## Install React libraries
npm install react react-dom

## Create app folder and files
mkdir app && cd app
touch index.html index.js index.css

At this point, trying to run this code in the browser will give an error as the browser does not understand JSX. This is where Babel and Webpack comes into play.

## Install required dependencies
npm install --save-dev @babel/core @babel/preset-env @babel/preset-react webpack webpack-cli webpack-dev-server babel-loader css-loader style-loader html-webpack-plugin

In case JSON parse issues run: npm cache clean --force

@babel/core: core API
@babel/preset-env: a preset that allows you to use the latest JavaScript without needing to micromanage which syntax transforms (and optionally, browser polyfills) are needed by your target environment(s).
@babel/preset-react: a preset that includes the plugins @babel/plugin-syntax-jsx, @babel/plugin-transform-react-jsx, @babel/plugin-transform-react-display-name
webpack: core API. Webpack is a bundler for modules. The main purpose is to bundle JS files for usage in a browser; yet it is also capable of transforming, bundling, or packaging just about any resource or asset.
webpack-cli: provides a flexible set of commands for developers to increase speed when setting up a custom webpack project. As of webpack v4, webpack is not expecting a configuration file, but often developers want to create a more custom webpack configuration based on their use-cases and needs. Webpack CLI addresses these needs by providing a set of tools to improve the setup of custom webpack configuration
webpack-dev-server: uses webpack with a development server that provides live reloading. This should be used for development only.
babel-loader: this package allows transpiling JavaScript files using Babel and Webpack.
css-loader: the css-loader interprets @import and url() like import.require() and will resolve them
style-loader: inject CSS into the DOM
html-webpack-plugin: simplifies the creation of HTML files to serve your webpack bundles. This is especially useful for webpack bundles that include a hash in the filename which changes every compilation. You can either let the plugin generate an HTML file for you, supply your own template using lodash templates, or use your own loader.

## Create Webpack config file
touch webpack.config.js

## Create Babel config file
Babel has two parallel config file formats, which can be used together, or independently
* Project-wide configuration
* File-relative configuration:
** .babelrc (and .babelrc.js) files
** package.json files with a "babel" key

## Add running scripts
"script": {
  "create": "webpack",
  "start": "webpack-dev-server --open"
}
