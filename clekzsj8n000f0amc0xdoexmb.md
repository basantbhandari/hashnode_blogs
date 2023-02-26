# What is polymorphism and what is its type

Polymorphism is a concept in object-oriented programming that allows objects of different classes to be treated as if they were objects of the same class. This allows for greater flexibility and code reuse, as well as more natural modeling of real-world situations where different objects may have similar behavior or properties.

There are two types of polymorphism in object-oriented programming:

1. Compile-time Polymorphism (also known as Method Overloading) Compile-time polymorphism occurs when there are multiple methods with the same name in a class, but with different parameters. The correct method to call is determined at compile-time based on the number and types of arguments passed to the method. Here's an example:
    

```csharp
csharpCopy codeclass MyClass
{
    public void MyMethod(int x)
    {
        // Method implementation...
    }
    
    public void MyMethod(string x)
    {
        // Method implementation...
    }
}
```

In this example, the `MyClass` class has two methods called `MyMethod`, but with different parameter types. The correct method to call is determined at compile-time based on the type of the argument passed to the method.

1. Runtime Polymorphism (also known as Method Overriding) Runtime polymorphism occurs when a derived class overrides a method of its base class with its own implementation. The correct method to call is determined at runtime based on the actual type of object that the method is called on. Here's an example:
    

```csharp
csharpCopy codeclass Shape
{
    public virtual void Draw()
    {
        Console.WriteLine("Drawing a shape...");
    }
}

class Circle : Shape
{
    public override void Draw()
    {
        Console.WriteLine("Drawing a circle...");
    }
}

class Rectangle : Shape
{
    public override void Draw()
    {
        Console.WriteLine("Drawing a rectangle...");
    }
}
```

In this example, the `Shape` the class has a virtual method called `Draw`, which is overridden in the `Circle` and `Rectangle` classes with their own implementations. When a `Draw` the method is called on an object of a derived class, and the implementation of the method that matches the actual type of the object is called at runtime.

Polymorphism allows for more flexible and extensible code, as well as more natural modeling of real-world situations where objects may have different behaviors or properties based on their type.