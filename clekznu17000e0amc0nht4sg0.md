# prevent a class from being inherited

In C#, you can prevent a class from being inherited by using the `sealed` keyword in the class definition. When a class is marked as `sealed`, it cannot be used as a base class for other classes, and no class can inherit from it. Here's an example:

```csharp
csharpCopy codesealed class MySealedClass
{
    // Class implementation...
}
```

In this example, the `MySealedClass` is marked as `sealed`, which means that it cannot be inherited from. If you try to inherit from this class, the C# compiler will generate an error.

Note that you can only use the `sealed` keyword on classes that are not themselves derived from other classes. If a class is derived from another class, it cannot be marked as `sealed`. Also, the `sealed` keyword can only be used on classes, not on interfaces or other types.