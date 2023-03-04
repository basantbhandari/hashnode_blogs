---
title: "decorator in c#"
datePublished: Sat Mar 04 2023 13:27:10 GMT+0000 (Coordinated Universal Time)
cuid: cleu00zk6000p09kz6dsthc53
slug: decorator-in-c
tags: decorator-in-c, decorator

---

In C#, a decorator is a design pattern that allows behavior to be added to an individual object dynamically, without affecting the behavior of other objects from the same class. It is achieved by creating a decorator class that wraps around the original object and provides additional functionality. Here's an example of how to implement a decorator in C#:

```csharp
// Define an interface for the object that we want to decorate
public interface IComponent
{
    void Operation();
}

// Create the concrete component class that implements the interface
public class ConcreteComponent : IComponent
{
    public void Operation()
    {
        Console.WriteLine("ConcreteComponent.Operation()");
    }
}

// Create the abstract decorator class that implements the interface
public abstract class Decorator : IComponent
{
    private IComponent component;

    public Decorator(IComponent component)
    {
        this.component = component;
    }

    public void Operation()
    {
        component.Operation();
    }
}

// Create the concrete decorator class that adds additional functionality
public class ConcreteDecorator : Decorator
{
    public ConcreteDecorator(IComponent component) : base(component)
    {
    }

    public override void Operation()
    {
        base.Operation();
        Console.WriteLine("ConcreteDecorator.Operation()");
    }
}

// Use the decorator
IComponent component = new ConcreteComponent();
component.Operation(); // outputs "ConcreteComponent.Operation()"

IComponent decoratedComponent = new ConcreteDecorator(new ConcreteComponent());
decoratedComponent.Operation(); // outputs "ConcreteComponent.Operation()" followed by "ConcreteDecorator.Operation()"
```

In this example, we define an interface `IComponent` that represents the object that we want to decorate. We then create a concrete component class `ConcreteComponent` that implements the interface.

We then define an abstract decorator class `Decorator` that also implements the interface and has a reference to the wrapped object. The `Operation()` method is implemented to call the wrapped object's `Operation()` method.

Finally, we create a concrete decorator class `ConcreteDecorator` that extends the `Decorator` class and adds additional functionality to the `Operation()` method.

To use the decorator, we can create an instance of the concrete component and call its `Operation()` method. We can then create an instance of the concrete decorator, passing the concrete component as an argument. When we call the decorated object's `Operation()` method, it will first call the wrapped object's `Operation()` method and then perform its additional functionality.