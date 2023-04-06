---
title: "What are custom elements?"
datePublished: Thu Apr 06 2023 15:34:38 GMT+0000 (Coordinated Universal Time)
cuid: clg5a40zc000809lb2gwl2teu
slug: what-are-custom-elements

---

Custom Elements is a web standard that allows developers to create their own custom HTML elements, with their own properties and methods, that can be used and reused across different web pages and applications.

Custom Elements are created using the `CustomElementRegistry.define()` method, which allows developers to define a new custom element by specifying its tag name, class definition, and any other options such as its shadow DOM, styles, and event listeners.

Here is an example of how to define a custom element:

```typescript
class MyElement extends HTMLElement {
  constructor() {
    super();
    // Initialize your custom element
  }
}

customElements.define('my-element', MyElement);
```

In this example, the `MyElement` class extends the built-in `HTMLElement` class, and provides custom functionality and behavior for the new element. The `customElements.define()` method registers the new element with the browser, and associates the tag name `my-element` with the `MyElement` class.

Once the custom element is defined, it can be used in HTML like any other element, and can be customized with attributes, properties, and events:

```typescript
<my-element id="myElement" data-value="42"></my-element>
```

In this example, the `my-element` custom element can be accessed using the `document.getElementById('myElement')` method, and its custom properties and methods can be called like any other object.

Custom Elements provide a powerful way to encapsulate and reuse functionality across different web pages and applications, and can help simplify and standardize web development.