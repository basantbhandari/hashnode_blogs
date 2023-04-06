---
title: "What are template expressions?"
datePublished: Thu Apr 06 2023 14:05:57 GMT+0000 (Coordinated Universal Time)
cuid: clg56xzhk001009mhddci7i50
slug: what-are-template-expressions
tags: angularjs

---

In Angular, template expressions are used to dynamically evaluate and display data in the template. They are JavaScript expressions that are evaluated within the context of the component's class and can access its properties and methods.

Template expressions are enclosed in double curly braces (`{{ }}`) and can include variables, operators, function calls, and other JavaScript syntax. They can also be used in conjunction with Angular's built-in directives to conditionally render content, iterate over arrays, and perform other dynamic behavior.

Here's an example of using a template expression to display the value of a component property in a template:

```typescript
<h1>Welcome, {{ username }}!</h1>
```

In this example, the `{{ username }}` template expression is used to display the value of the `username` property defined in the component's TypeScript code.

Template expressions can also include function calls, such as:

```typescript
<button (click)="increaseCount()">Click me</button>
<p>You've clicked the button {{ count }} times</p>
```

In this example, the `(click)` event binding is used to call the `increaseCount()` method when the button is clicked, and the `{{ count }}` template expression is used to display the value of the `count` property, which is updated by the `increaseCount()` method.

Overall, template expressions are a powerful and flexible feature of Angular's templating system that allows you to create dynamic, data-driven UIs.