# React + Typescript + Sass Boilerplate using Webpack

## Download the Boilerplate

`npx degit https://github.com/lifeanddoodles/react-typescript-webpack-starter app-name`

## Install Dependencies

Go to your project folder, for example: `cd app-name`  
`npm install`

## Run Dev Server

`npm run start`

## Build

`npm run build`

## Env Variables

With Webpack we can define our own variables.

### Define Variables in Development

In `/webpack/webpack.dev.js`, at the top add:

```javascript
const webpack = require('webpack')
```

Inside the plugins array add:

```javascript
plugins: [
...
new webpack.DefinePlugin({
'process.env.yourvariablename': JSON.stringify('valueindev'),
}),
],
```

### Define Variables in Production

In `/webpack/webpack.prod.js`, at the top add:

```javascript
const webpack = require('webpack')
```

Inside the plugins array add:

```javascript
plugins: [
...
new webpack.DefinePlugin({
'process.env.yourvariablename': JSON.stringify('valueinprod'),
}),
],
```

**Note:** if you use the same value for both environments just make the corresponding changes to the `/webpack/webpack.common.js` file.

### Use Env Variables

To use in the application just add `{ process.env.yourvariablename }` to the part where it's needed.
