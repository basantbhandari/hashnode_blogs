---
title: "How do you create and use middleware in Node.js?"
datePublished: Sat Apr 08 2023 13:38:09 GMT+0000 (Coordinated Universal Time)
cuid: clg80txxv01e6pxnv634qea9y
slug: how-do-you-create-and-use-middleware-in-nodejs

---

Middleware is a function that takes three arguments: the request object, the response object, and the next function.

To create middleware, you can use the built-in middleware functions in the Node.js standard library, or you can create your own.

To use middleware, you need to register it with the app. use() method. This method takes the path and the middleware function as arguments.

The middleware function is called when the app receives a request. If the middleware function doesn’t call the next function, the request will be left hanging.

If the middleware function calls next(), the request will be passed to the next middleware function in the stack.