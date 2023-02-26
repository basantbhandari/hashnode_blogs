# difference between readonly and constant in c#

In C#, both "readonly" and "const" are used to create variables that cannot be modified at runtime, but they have some differences:

1. "const" keyword: A "const" variable is a compile-time constant, which means its value is determined at compile-time and cannot be changed at runtime. A "const" variable must be initialized with a value, and that value must be a literal, a constant expression, or an enumeration member.
    

Syntax:

```cpp
public const int MaxValue = 100;
```

Example:

```c
const double Pi = 3.14159;
```

In this example, the "Pi" variable is a compile-time constant with the value of 3.14159, and it cannot be changed at runtime.

1. "readonly" keyword: A "readonly" variable is a runtime constant, which means its value is determined at runtime and can be changed only in the constructor of the class in which it is defined. A "readonly" variable can be initialized with a value or can be left uninitialized, in which case it must be initialized in the constructor.
    

Syntax:

```csharp
public readonly int MaxValue;
```

Example:

```csharp
readonly string Greeting;

public MyClass(string greeting)
{
    Greeting = greeting;
}
```

In this example, the "Greeting" variable is a runtime constant that is initialized in the constructor of the "MyClass" class, and it cannot be changed after that.

Overall, the main difference between "const" and "readonly" is that "const" creates a compile-time constant, while "readonly" creates a runtime constant that can be initialized at runtime. "Const" variables are generally used for values that never change, while "readonly" variables are used for values that are constant for a particular instance of a class, but can vary between different instances of the same class.