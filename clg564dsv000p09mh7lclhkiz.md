---
title: "What is the purpose of the async pipe?"
datePublished: Thu Apr 06 2023 13:42:56 GMT+0000 (Coordinated Universal Time)
cuid: clg564dsv000p09mh7lclhkiz
slug: what-is-the-purpose-of-the-async-pipe
tags: async-pipe

---

In Angular, the async pipe is a built-in pipe that provides a convenient way to handle asynchronous data in templates. Its purpose is to subscribe to an Observable or Promise and automatically update the view when new data is emitted or returned.

The async pipe is particularly useful when working with Observables, as it automatically subscribes to the Observable and unsubscribes when the component or template is destroyed, preventing memory leaks.

Here is an example of how the async pipe is used:

```typescript
import { Component } from '@angular/core';
import { Observable } from 'rxjs';
import { DataService } from './data.service';

@Component({
  selector: 'app-example',
  template: `
    <h1>{{ title }}</h1>
    <ul>
      <li *ngFor="let item of items$ | async">{{ item }}</li>
    </ul>
  `
})
export class ExampleComponent {
  title = 'Example Component';
  items$: Observable<string[]>;

  constructor(private dataService: DataService) {}

  ngOnInit() {
    this.items$ = this.dataService.getItems();
  }
}
```

In this example, the `ExampleComponent` requests an Observable of items from the `DataService` class and assigns it to the `items$` property. The async pipe is used in the template to subscribe to the Observable and automatically update the view with the latest data.

The `*ngFor` the directive is used to iterate over the array of items emitted by the Observable, and the async pipe is used to unwrap the Observable and provide the latest array of items to the directive.

By using the async pipe, the component does not need to manually subscribe to the Observable, and the view is automatically updated when new data is emitted. This helps to simplify the code and prevent memory leaks by handling subscriptions and unsubscriptions automatically.