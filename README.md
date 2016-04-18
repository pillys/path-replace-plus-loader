# path-replace-plus-loader for webpack

Path replace loader(plus) for [webpack](http://webpack.github.io/). Replace a or some given base path with another path for dynamic module loading. Great for large applications with locally overridable modules.

## Installation

`npm install path-replace-plus-loader`

## Usage

[Read more about using loaders](http://webpack.github.io/docs/using-loaders.html)

#### Configuration
- <b>list:</b> An array of replace rules

The rules must be like:

- <b>path:</b> Absolute original path to replace, e.g. __dirname/app/core
- <b>replacePath:</b> Absolute replacement path, e.g. __dirname/app/local

#### webpack config example

``` js
module.exports = {
  module: {
    loaders: [
      {
        test: /\.js$/,
        loader: 'path-replace-plus',
        query: {
          list: [{
            path: 'ORIGINAL_PATH 1',
            replacePath: 'REPLACE_PATH 1'
          },{
            path: 'ORIGINAL_PATH 2',
            replacePath: 'REPLACE_PATH 2'
          }]
        }
      }
    ]
  }
};
```

#### Example

``` js
// Loader tries to load from local directory if file exists app/local/modules/auth
var authModule = require('app/core/modules/auth');
```

## [MIT License](http://www.opensource.org/licenses/mit-license.php)
