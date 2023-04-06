---
title: "Do I need to bootstrap custom elements?"
datePublished: Thu Apr 06 2023 15:37:13 GMT+0000 (Coordinated Universal Time)
cuid: clg5a7cr4000009msfcwk059g
slug: do-i-need-to-bootstrap-custom-elements
tags: angularjs

---

No, you do not need to bootstrap custom elements in the same way you would bootstrap an Angular application. Custom elements are standalone web components that can be used in any web page, without requiring a framework or runtime environment to load them.

When you define a custom element using the `customElements.define()` method, the browser automatically registers it with the DOM, and you can use it in HTML like any other HTML element. You do not need to manually bootstrap or initialize the custom element, as the browser takes care of instantiating and rendering it for you.

However, if you are using a framework like Angular, React, or Vue, you may need to take some additional steps to integrate your custom elements with the framework. For example, you may need to create a wrapper component that provides an interface for interacting with the custom element, or you may need to use a library like `@webcomponents/custom-elements` to enable compatibility with older browsers.

In general, if you are using custom elements in a standalone web application or as part of a library or package, you do not need to worry about bootstrapping them. However, if you are integrating custom elements with a larger application or framework, you should consult the documentation for your specific framework to determine the best way to use and integrate custom elements.