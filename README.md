# Laravel Mix SVG

A laravel mix plugin that adds a `svg.js` file to your project. This is the JavaSript counterpart to Adam's Laravel Blade SVG composer package.

## Install

```bash
npm install --save-dev laravel-mix-svg
```

Add the following to your `webpack.mix.js` file
```javascript
mix.svg();
```

## Usage

By default it grabs any svg file from your `resources/assets/svg` folder and makes it available as the filename without extension.
It creates a new file called `resources/assets/js/svg.js` that contains a single public method to render a svg method.

```javascript
const svg = require('./svg')

svg('my-thing'); // Spits out svg tag of the file my-thing.svg
svg('my-thing', 'icon bg-blue'); // Adds icon & bg-blue css class to the svg.
```

With VueJs

```
Vue.prototype.svg = require('./svg');
```

Insisde a template tag you can use `v-html` to render out a svg image.
```html
<template>
...
<span v-html="svg('my-thing', 'icon bg-blue')" />
...
```

## Configuration

You can give a object to `mix.svg` 

```javascript
mix.svg({
  class: 'icon', // Applied to all svg's
  assets: ['./resources/svg/'], // a list of directories to search svg images
  output: './resources/js/svg.js', // Where the craeted js file needs to go.
})
```
