---
title: "What is the purpose of the ngIf directive?"
datePublished: Thu Apr 06 2023 13:59:12 GMT+0000 (Coordinated Universal Time)
cuid: clg56paxo000709l9gcn1d69y
slug: what-is-the-purpose-of-the-ngif-directive
tags: angular

---

In Angular, the `ngIf` directive is used to conditionally render content based on a boolean expression. It evaluates the expression and only renders the content if the expression is true, otherwise, it removes the content from the DOM.

Here's an example of using the `ngIf` directive to conditionally render a component:

```typescript
<div *ngIf="isLoggedIn">
  <app-profile></app-profile>
</div>
```

In this example, the `ngIf` directive is used with the `*` syntax to conditionally render the `app-profile` component based on the value of the `isLoggedIn` variable. If `isLoggedIn` is `true`, the `app-profile` component will be rendered within the `div` element. If `isLoggedIn` is `false`, the `div` element and its contents will be removed from the DOM.

The `ngIf` directive is commonly used in Angular templates to conditionally show or hide elements based on user actions, authentication status, or other dynamic conditions. It can also be used to improve performance by reducing the amount of content that needs to be rendered in the DOM.