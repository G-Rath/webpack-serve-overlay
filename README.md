# webpack-serve-overlay

A rudimentary overlay for [`webpack-serve`](https://github.com/webpack-contrib/webpack-serve), based off the one used in `webpack-dev-server`.

This package is targeted at serves as a quick fully functional way of 
being able to have the same overlay as `webpack-dev-server` in `webpack-serve` with minimal fuss & expense.

## Usage

Install the package:

```
npm i webpack-serve-overlay
```

Then add the following entry to the [`entry` object](https://webpack.js.org/configuration/entry-context/#entry) in your webpack config:

```javascript
overlay: 'webpack-serve-overlay/onlyIfDevelopment'
```

and you'll be away laughing.

_NOTE: If you are using the default `webpack-hot-client` options, you will want to make sure that this is **not** your first entry. [More info](https://github.com/webpack-contrib/webpack-serve/issues/119#issuecomment-401502247)_  

For a more custom installation, you can alternatively require the overlay at the top of your `index.jsx` (or equivalent):

```javascript
// becomes dead code in builds other than dev,
// which webpack should pick up and remove.
if(process.env.NODE_ENV === 'development') {
    require('webpack-serve-overlay');
}
```



## Configuration

The overlay works by using a WebSocket that connects to `webpack-serve` à la `webpack-hot-client`.  
This means that it *shouldn't* require any extra settings or configuration.

However, just in case, you can manually specify the WebSocket url by setting the `WEBPACK_SERVE_OVERLAY_WS_URL` env property.
