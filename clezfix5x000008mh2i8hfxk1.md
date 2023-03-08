---
title: "Async / Await in Dotnet"
datePublished: Wed Mar 08 2023 08:39:51 GMT+0000 (Coordinated Universal Time)
cuid: clezfix5x000008mh2i8hfxk1
slug: async-await-in-dotnet
tags: async-await-in-dotnet

---

Asynchronous programming in .NET allows you to write code that can execute without blocking the main thread. This is achieved using the `async` and `await` keywords.

Here's an example of how to use `async` and `await` in C#:

```csharp
using System;
using System.Threading.Tasks;

class Program {
    static async Task Main(string[] args) {
        Console.WriteLine("Before delay");

        // This line will execute asynchronously
        await Task.Delay(1000);

        Console.WriteLine("After delay");
    }
}
```

In this example, we define a `Main` the method that is marked as `async` and returns a `Task`. Inside the method, we first write a message to the console indicating that we are about to execute an asynchronous operation.

We then call the `Task.Delay` method, which returns a `Task` that completes after the specified delay (in this case, one second). We use the `await` keyword to wait for this `Task` to complete before executing the next line of code.

Finally, we write a message to the console indicating that the asynchronous operation has been completed.

When you run this code, you should see the message "Before delay" printed to the console, followed by a one-second delay, and then the message "After delay" printed to the console.

Note that `async` and `await` are not only useful for waiting on asynchronous operations like network requests or file I/O, but they can also be used to improve the responsiveness of UI applications by allowing the main thread to continue processing user input while long-running operations execute in the background.

here's another example that demonstrates how to use `async` and `await` with the `HttpClient` class to make an asynchronous HTTP request:

```csharp
using System;
using System.Net.Http;
using System.Threading.Tasks;

class Program {
    static async Task Main(string[] args) {
        // Create an instance of the HttpClient class
        HttpClient client = new HttpClient();

        // Make an asynchronous HTTP GET request
        HttpResponseMessage response = await client.GetAsync("https://jsonplaceholder.typicode.com/todos/1");

        // Read the response body as a string
        string responseBody = await response.Content.ReadAsStringAsync();

        // Write the response body to the console
        Console.WriteLine(responseBody);
    }
}
```

In this example, we first create an instance of the `HttpClient` class, which is used to make HTTP requests. We then call the `GetAsync` method of the `HttpClient` class to make an asynchronous HTTP GET request to the specified URL.

We use the `await` keyword to wait for the `GetAsync` method to complete and return a `HttpResponseMessage` object.

We then call the `ReadAsStringAsync` method of the `HttpContent` an object that is contained in the `HttpResponseMessage` object to read the response body as a string. Again, we use the `await` keyword to wait for this asynchronous operation to complete.

Finally, we write the response body to the console using the `Console.WriteLine` method.

When you run this code, you should see the response body of the HTTP GET request printed to the console. Note that because the HTTP request is made asynchronously, the main thread can continue processing other tasks while the request is being made, which can help improve the responsiveness of your application.