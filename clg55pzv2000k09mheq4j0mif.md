---
title: "What is metadata, in angular"
datePublished: Thu Apr 06 2023 13:31:45 GMT+0000 (Coordinated Universal Time)
cuid: clg55pzv2000k09mheq4j0mif
slug: what-is-metadata-in-angular
tags: metadata-in-angular

---

In Angular, metadata is a way to provide additional information about a class, such as a component or a service, that is not part of the class's implementation. Metadata is defined using decorators, which are functions that modify the behavior of a class or its members.

The metadata for a class is stored in an object called the metadata object. This object contains key-value pairs that provide information such as the selector for a component, the dependencies for a service, or the route path for a module.

For example, the @Component decorator is used to define metadata for a component in Angular. This decorator takes an object that contains properties such as selector, template, styleUrls, and providers, which are used to define the behavior and appearance of the component.

Here is an example of how metadata is used in Angular:

```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-example',
  template: `
    <h1>{{ title }}</h1>
    <p>{{ message }}</p>
  `,
  styleUrls: ['./example.component.css']
})
export class ExampleComponent {
  title = 'Example Component';
  message = 'Hello, world!';
}
```

In this example, the @Component decorator is used to define the metadata for the ExampleComponent class. The selector property specifies the CSS selector for the component, the template property defines the HTML template for the component, and the styleUrls property specifies the CSS styles for the component.