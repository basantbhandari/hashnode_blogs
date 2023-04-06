---
title: "How is Dependency Hierarchy formed?"
datePublished: Thu Apr 06 2023 13:39:54 GMT+0000 (Coordinated Universal Time)
cuid: clg560hjw000g0alb985db9qo
slug: how-is-dependency-hierarchy-formed
tags: angularjs

---

In Angular, a dependency hierarchy is formed through the dependency injection (DI) mechanism. In DI, an object or a component's dependencies are provided externally rather than created within the object or component itself. This allows for more flexibility and testability of the application, as dependencies can be easily swapped out or mocked for testing.

The hierarchy of dependencies is formed by the injector, which is responsible for providing dependencies to objects or components. The injector maintains a hierarchical structure of injectors, with the root injector at the top and child injectors below it.

The root injector is created when the Angular application is bootstrapped and provides services and dependencies that are common to the entire application. Child injectors can be created for specific components or modules and inherit dependencies from their parent injectors.

The hierarchy of injectors forms a tree-like structure, with each injector having its own set of providers that define the dependencies it provides. When an object or component requests a dependency, the injector searches the hierarchy starting from the closest injector and works its way up the tree until it finds a provider that can fulfill the request.

Here is an example of how dependency hierarchy is formed in Angular:

```typescript
import { Component } from '@angular/core';
import { MyService } from './my.service';

@Component({
  selector: 'app-example',
  template: `
    <h1>{{ title }}</h1>
    <p>{{ message }}</p>
  `,
  providers: [MyService]
})
export class ExampleComponent {
  title = 'Example Component';
  message: string;

  constructor(private myService: MyService) {}

  ngOnInit() {
    this.message = this.myService.getMessage();
  }
}
```

In this example, the `ExampleComponent` requests a dependency on the `MyService` class through its constructor. The `MyService` class is provided to the component through its provider array in the `@Component` decorator. When the component is created, the injector searches for a provider for `MyService` starting from the component's own injector and working its way up the hierarchy until it finds a provider. Once a provider is found, an instance of `MyService` is created and injected into the component's constructor, which can then use the service to retrieve a message to display in the component's view.