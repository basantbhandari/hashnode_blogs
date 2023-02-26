# different type of inheritance with example in c#

Sure, here are some examples of the different types of inheritance in C#:

<mark>Single Inheritance:</mark> Single inheritance involves deriving a new class from a single base class. In the following example, we define a base class called `Animal` and a derived class called `Dog` that inherits from `Animal`.

```csharp
class Animal
{
    public void Eat()
    {
        Console.WriteLine("Animal is eating.");
    }
}

class Dog : Animal
{
    public void Bark()
    {
        Console.WriteLine("Dog is barking.");
    }
}
```

Here, the `Dog` class inherits the `Eat()` method from the `Animal` class and adds its own `Bark()` method.

<mark>Multiple Inheritance</mark>**:** Multiple inheritance involves deriving a new class from two or more base classes. However, C# does not support multiple inheritance of classes, but it does support multiple inheritance of interfaces. In the following example, we define two interfaces `IWalk` and `IRun`, and a class called `Horse` that implements both interfaces.

```csharp
csharpCopy codeinterface IWalk
{
    void Walk();
}

interface IRun
{
    void Run();
}

class Horse : IWalk, IRun
{
    public void Walk()
    {
        Console.WriteLine("Horse is walking.");
    }

    public void Run()
    {
        Console.WriteLine("Horse is running.");
    }
}
```

Here, the `Horse` class implements both `IWalk` and `IRun` interfaces, which means it must provide implementations for the `Walk()` and `Run()` methods defined in both interfaces.

<mark>Hierarchical Inheritance:</mark> Hierarchical inheritance involves deriving multiple classes from a single base class. In the following example, we define a base class called `Vehicle` and two derived classes `Car` and `Truck` that both inherit from `Vehicle`.

```csharp
csharpCopy codeclass Vehicle
{
    public void Drive()
    {
        Console.WriteLine("Vehicle is driving.");
    }
}

class Car : Vehicle
{
    public void Honk()
    {
        Console.WriteLine("Car is honking.");
    }
}

class Truck : Vehicle
{
    public void Load()
    {
        Console.WriteLine("Truck is loading.");
    }
}
```

Here, both the `Car` and `Truck` classes inherit the `Drive()` method from the `Vehicle` class, but add their own methods, `Honk()` and `Load()` respectively.

<mark>Multilevel Inheritance</mark>: Multilevel inheritance involves deriving a new class from a derived class. In the following example, we define a base class called `Person`, a derived class called `Employee` that inherits from `Person`, and another derived class called `Manager` that inherits from `Employee`.

```csharp
csharpCopy codeclass Person
{
    public void Speak()
    {
        Console.WriteLine("Person is speaking.");
    }
}

class Employee : Person
{
    public void Work()
    {
        Console.WriteLine("Employee is working.");
    }
}

class Manager : Employee
{
    public void Manage()
    {
        Console.WriteLine("Manager is managing.");
    }
}
```

Here, the `Manager` the class inherits both the `Speak()` and `Work()` methods from the `Person` and `Employee` classes, respectively, and adds its own `Manage()` method.