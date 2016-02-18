# vue-animated-list

A Vue.js plugin for easily animating `v-for` rendered lists.

[Live Demo](http://vuejs.github.io/vue-animated-list/example.html)

Compatibility: [IE10+](http://caniuse.com/#search=css%20transition).

## Installation

- #### With Modules

  ``` js
  // ES6
  import Vue from 'vue'
  import VueAnimatedList from 'vue-animated-list'
  Vue.use(VueAnimatedList)

  // ES5
  var Vue = require('vue')
  Vue.use(require('vue-animated-list'))
  ```

- #### `<script>` Include

  Just include `vue-animated-list.js` after Vue itself.

## Usage

There's nothing you need to do in JavaScript except for installation. In your markup, make sure the `v-for` has a transition attribute:

``` html
<div v-for="item in items" transition="item">
  {{ item.text }}
</div>
```

Now, all you need to do is define the `.item-move` CSS class:

``` css
.item-move {
  /* applied to the element when moving */
  transition: transform .5s cubic-bezier(.55,0,.1,1);
}
```

And that's it! You can also add CSS classes for enter and leave transitions - they all work nicely together!

A few things to note:

1. The animation is done using the CSS `transform` property. So make sure when `.item-move` is applied its `transform` property is transition-enabled.

2. Move animations can only work on elements, so it doesn't work for `<template v-for>` and fragment instance components.
