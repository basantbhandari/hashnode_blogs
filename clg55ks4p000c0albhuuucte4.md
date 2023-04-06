---
title: "Angular architecture"
datePublished: Thu Apr 06 2023 13:27:41 GMT+0000 (Coordinated Universal Time)
cuid: clg55ks4p000c0albhuuucte4
slug: angular-architecture
tags: angular-architecture

---

1. Modules: Angular applications are organized into modules, which are a collection of components, services, directives, and pipes that are related to a specific functionality or feature of the application. Each Angular application has at least one root module, called the app module, which bootstraps the application.
    
2. Components: Components are the building blocks of an Angular application's user interface. Each component encapsulates a piece of functionality or a part of the user interface and consists of a template, which defines the component's view, and a class, which defines the component's behavior.
    
3. Templates: Templates are HTML files that define the structure and layout of a component's view. Templates can include Angular directives and binding syntax, which allow the component to interact with the application's data model and respond to user input.
    
4. Services: Services are singleton objects that provide functionality that can be shared across multiple components. Services are used to encapsulate business logic, data access, and other application logic that is not specific to a particular component.
    
5. Directives: Directives are instructions that are applied to elements in a template to modify their behavior or appearance. Angular provides a set of built-in directives, such as ngFor and ngIf, that allow developers to manipulate the component tree based on the application's data model.
    
6. Pipes: Pipes are a way to transform data in an Angular application. Pipes can be used to format dates, numbers, and other types of data, or to filter and sort arrays.
    
7. Dependency Injection: Dependency injection is a pattern used to provide instances of objects that a class needs to perform its work. In Angular, dependency injection is used extensively to provide instances of services to components and other objects that need them.
    
8. RxJS: RxJS is a library for reactive programming in JavaScript. Angular uses RxJS for handling asynchronous operations such as HTTP requests.
    
9. Zone.js: Zone.js is a library for managing asynchronous operations in JavaScript. Angular uses Zone.js to detect and track changes to the application state.