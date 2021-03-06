# simple-vue-js

Table of Contents
==================

* [Installing Vue](#installing-vue)
* [Installing Axios](#installing-axios)
* [Initialising an Instance of Vue](#initialising-an-instance-of-vue)

## Prerequisites

* HTML
* CSS
* JavaScript

## Pros

- Simplicity
    - Templates
    - Declarative Bindings
- Speed
- Licensing
- Browser Support
- Easy to learn
- Easy to use

### Templates

Separate the UI from the data in the business logic. The data and business logic
is written in JavaScript and the UI is defined by HTML and CSS. Vue is then
responsible for compiling the templates into what the user sees. 
* Minimises the amount of code you have to write. 
* Protect you from changes. Instead of the UI being driven by the HTML, 
the UI is driven by the data. The UI and the data are bound together by 
`Declarative Bindings.`

### Declarative Bindings

This is the glue that hold the UI and the data together. They enable a 
separation of concerns that enables simplicity in development. It removes
the burden of directly managing the DOM (Document Object Model)
when the data changes.

## Installing Vue

In order to add Vue, you will need to add a script tag that will inject the 
Vue library through a CDN (Content delivery network). To install Vue in your 
app you will need to add the following `script` tag:

```html
<!doctype html>
<html>
    <head>
        <title>MyVue</title>
    </head>
    <body>
        <div id="myVue"></div>
        <script type="text/javascript" src="https://unpkg.com/vue"></script>
    </body>
</html>
```

## Installing Axios

Axios is the recommended library for making HTTP requests from Vue. It's 
one of the popular HTTP clients available through `unpkg` and we can use
within our Vue apps. To install Axios in your Vue app you will need to add
the following script tag:

```html
<!doctype html>
<html>
    <head>
        <title>MyVue</title>
    </head>
    <body>
        <div id="myVue"></div>
        <script type="text/javascript" src="https://unpkg.com/vue"></script>
        <script type="text/javascript" 
        src="https://unpkg.com/axios/dist/axios.min.js"></script>
    </body>
</html>
```

## Initialising an Instance of Vue

```javascript
var myVue = new Vue({
    el: '#myVue',
    data: {     
    }
});
```

## Mounting an Instance of Vue

This is when the virtual DOM is actually shown to the user. In other words this is when your 
view becomes visible to the user.

To mount an instance of view onto the DOM use the `el` option in the Vue constructor.

You mainly have 2 main options:
- You can assign it to the HTML element:
```javascript
var growler = new Vue({
    el: document.getElementById('growler')
});
```

- You can use a CSS selector
```javascript
var growler = new Vue({
    el: '#growler',
});
```
The CSS selector approach it preferred as it is more readable :smile:.

**Mounting an instance of Vue actually replaces the HTML DOM element with the Vue generated DOM
for that reason, YOU SHOULD NEVER SET THE `el` OPTION TO THE HTML OR BODY ELEMENTS IN A WEBPAGE**

# Vue Lifecycle
<p align="center">
  <img src="https://user-images.githubusercontent.com/29547780/36276240-2d862ec4-1285-11e8-9471-675a59639eb4.png">
</p>

## New Vue()

## Creation

`Creation hooks` are the very first hooks that run in your component. 
They allow you to perform actions before your component has even been added to the DOM. 
Unlike any of the other hooks, creation hooks are also run during server-side rendering.

Use creation hooks if you need to set things up in your component both during client 
rendering and server rendering. 
You will not have access to the DOM or the target mounting element (`this.$el`) 
inside of creation hooks.

### beforeCreate
The `beforeCreate` hook runs at the very initialization of your component were `data` has not been made reactive, 
and `events` have not been set up yet.

Example:
```javascript
<script>
export default {
  beforeCreate() {
    console.log('Nothing gets called before me!')
  }
}
</script>
```

### created
In the created hook, you will be able to access reactive data and events are active. Templates and Virtual DOM have 
not yet been mounted or rendered.

Example:
```javascript
<script>
export default {
  data() {
    return {
      property: 'Blank'
    }
  },

  computed: {
    propertyComputed() {
      console.log('I change when this.property changes.')
      return this.property
    }
  },

  created() {
    this.property = 'Example property update.'
    console.log('propertyComputed will update, as this.property is now reactive.')
  }
}
</script>
```

## Mounting

## Updating

## Destroy
