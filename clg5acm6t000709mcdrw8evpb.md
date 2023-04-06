---
title: "define typings for custom elements?"
datePublished: Thu Apr 06 2023 15:41:19 GMT+0000 (Coordinated Universal Time)
cuid: clg5acm6t000709mcdrw8evpb
slug: define-typings-for-custom-elements
tags: typings-for-custom-elements

---

Defining typings for custom elements involves creating an interface that describes the properties and methods of the custom element, and then using this interface to type-check the element in your code.

To define typings for a custom element, you can create a TypeScript interface that extends the `HTMLElement` interface and defines any custom properties and methods that your element provides. Here is an example:

```typescript
interface MyElement extends HTMLElement {
  foo: string;
  bar(): void;
}
```

In this example, the `MyElement` interface extends the `HTMLElement` interface, and adds two custom properties: `foo`, which is a string, and `bar`, which is a function that takes no arguments and returns void.

You can then use this interface to type-check any references to your custom element in your code. For example:

```typescript
const myElement = document.querySelector('my-element') as MyElement;
myElement.foo = 'Hello, world!';
myElement.bar();
```

In this example, the `document.querySelector()` method returns an `HTMLElement` an object that is cast to the `MyElement` interface using the `as` keyword. This allows you to access the custom properties and methods of the element with type-checking and autocompletion support from TypeScript.

Defining typings for custom elements can help improve the readability and maintainability of your code, as well as catch errors at compile time rather than runtime. However, it is important to note that typings are a compile-time feature of TypeScript, and do not provide any runtime enforcement of the types or interfaces you define.