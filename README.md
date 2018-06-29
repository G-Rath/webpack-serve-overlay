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

Then add the following entry to the `entry` object in your webpack config:

```
overlay: require.resolve('webpack-serve-overlay')
```

and you'll be away laughing.


## Problems

Tons.

This overlay currently is hardcoded to try to connect to `ws://localhost:8081`.
That's absolutely the first thing I'm going to fix, but for now it works for me.
