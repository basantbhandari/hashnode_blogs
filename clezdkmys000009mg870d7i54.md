---
title: "Creating and Consuming Events in Dotnet"
datePublished: Wed Mar 08 2023 07:45:12 GMT+0000 (Coordinated Universal Time)
cuid: clezdkmys000009mg870d7i54
slug: creating-and-consuming-events-in-dotnet
tags: creating-and-consuming-events-in-dotnet, events-in-dotnet

---

In .NET, events are a way for objects to notify other objects when something interesting happens. An event is basically a delegate that allows other objects to subscribe to it and be notified when it is raised.

Here's an example of how to create and consume events in C#:

```csharp
using System;

class Program {
    static void Main(string[] args) {
        // Create an instance of the Publisher class
        Publisher publisher = new Publisher();

        // Subscribe to the event raised by the Publisher class
        publisher.SomeEvent += Subscriber;

        // Raise the event
        publisher.RaiseEvent();
    }

    static void Subscriber(object sender, EventArgs e) {
        Console.WriteLine("Event received!");
    }
}

class Publisher {
    // Declare an event using the EventHandler delegate
    public event EventHandler SomeEvent;

    public void RaiseEvent() {
        // Check if there are any subscribers to the event
        if (SomeEvent != null) {
            // Raise the event
            SomeEvent(this, EventArgs.Empty);
        }
    }
}
```

In this example, we first define a `Publisher` class that declares an event using the `EventHandler` delegate. The `Publisher` class also has a method `RaiseEvent` that raises the event if there are any subscribers.

In the `Main` method, we create an instance of the `Publisher` class and subscribe to the event using the `+=` operator. We then raise the event by calling the `RaiseEvent` method on the publisher object.

Finally, we define a `Subscriber` method that will be called when the event is raised. The `Subscriber` method simply writes a message to the console indicating that the event has been received.

When you run this code, you should see the message "Event received!" printed to the console. Note that you can have multiple subscribers to an event, and they will all be notified when the event is raised.