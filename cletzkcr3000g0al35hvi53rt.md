---
title: "how to write a callback function in c#"
datePublished: Sat Mar 04 2023 13:14:14 GMT+0000 (Coordinated Universal Time)
cuid: cletzkcr3000g0al35hvi53rt
slug: how-to-write-a-callback-function-in-c
tags: callback-function-in-c

---

In C#, a callback function is a method that is passed as an argument to another method and is called by the other method when a certain event occurs. Here's an example of how to write a callback function in C#:

```csharp
// Define the callback function signature
delegate void CallbackFunction(string message);

// Create a method that accepts a callback function as an argument
public void DoSomethingAsync(CallbackFunction callback)
{
    // Simulate some asynchronous operation
    System.Threading.Thread.Sleep(1000);
    
    // Call the callback function with a message
    callback("Operation complete");
}

// Define a callback function to use
public void MyCallback(string message)
{
    Console.WriteLine(message);
}

// Call the DoSomethingAsync method with the MyCallback function as the callback
DoSomethingAsync(MyCallback);
```

In this example, we define a delegate that defines the signature of the callback function. We then create a method `DoSomethingAsync` that accepts a callback function of this type as an argument. Inside the method, we perform some asynchronous operations and then call the callback function with a message.

Finally, we define a callback function `MyCallback` that matches the signature of the delegate and simply writes the message to the console. We then call `DoSomethingAsync` with `MyCallback` as the callback function. When `DoSomethingAsync` completes its operation, it will call `MyCallback` with the message "Operation complete".