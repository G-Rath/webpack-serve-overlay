# webpack-serve-overlay

A rudimentary overlay for webpack-serve, based off the one used in `webpack-dev-server`.

This overlay is currently in development. It's fully working, 
but has none of the clever automagical features like inserting itself into `webpack.entry`.

These features (and more) should hopefully come with time. Right now this package serves as a quick fully functional way of 
being able to have the same overlay as `webpack-dev-server` in `webpack-serve` with minimal fuss & expense.

## Usage

Install the package:

```
npm i webpack-serve-overlay
```

Then import the overlay at the top of your `index.jsx` (or equivalent):

```javascript
// becomes dead code in builds other than dev,
// which webpack should pick up and remove.
if(process.env.NODE_ENV === 'development') {
    import 'webpack-serve-overlay';
}
```

and you'll be away laughing.

## Configuration

The overlay works by using a WebSocket that connects to `ws://localhost:8081` by default.

This value can be overridden by setting the `WEBPACK_SERVE_OVERLAY_WS_URL` env property.

I aim to replace later add functionality to get this (and similar) values from `webpack-serve` itself.
