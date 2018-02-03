# simple-vue-js

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

## Adding Vue

In order to add Vue, you will need to add a script tag that will inject the 
Vue library through a CDN (Content delivery network).

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