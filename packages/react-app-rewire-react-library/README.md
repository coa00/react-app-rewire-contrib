# react-app-rewire-react-umd-library

Enable output of umd and css.

Fork [react-app-rewire-react-library](https://github.com/osdevisnot/react-app-rewire-contrib/tree/master/packages/react-app-rewire-react-library)

## Installation

```
yarn add --dev react-app-rewire-react-umd-library

# or use npm if you don't have yarn yet

npm install --save-dev react-app-rewire-react-umd-library
```

## Usage
In the `config-overrides.js` you created for [react-app-rewired](https://github.com/timarney/react-app-rewired) add this code:

```
const rewireCreateReactLibrary = require('react-app-rewire-react-library');

module.exports = function override(config, env) {
  config = rewireCreateReactLibrary(config, env);
  return config;
};
```

In `package.json`, add a separate npm script to build library

```
{
  "main": "./build/library.js",
  "outCss": "./build/library.css", // optional
  "outHtml": "./build/library.html", // optional
  "libraryTarget": "umd", // or commonjs
  "scripts": {
    ...
    "build-library": "react-app-rewired build --library",
    ...
  }
}
```
