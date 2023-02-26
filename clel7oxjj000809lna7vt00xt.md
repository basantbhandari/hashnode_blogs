# boxing and unboxing in Dotnet

In .NET, boxing is the process of converting a value type to a reference type, and unboxing is the reverse process of converting a reference type to a value type.

Boxing occurs when a value type, such as an integer or a struct, is assigned to a variable of type `object` or one of its derived types, such as `System.ValueType`. When the value is boxed, a new object is created on the heap that contains the value of the original value type.

Unboxing is the process of extracting the value type from the object created during boxing. To unbox a value type, you must cast the reference type to the value type. If the cast is invalid or the object does not contain the expected value type, an `InvalidCastException` is thrown.

Here's an example of boxing and unboxing in C#:

```csharp
int i = 42; // declare an int variable
object obj = i; // box the int into an object

int j = (int)obj; // unbox the object back into an int

Console.WriteLine(j); // prints 42
```

In this example, the `int` value `42` is boxed into an `object`, and then unboxed back into an `int`. Boxing and unboxing can have performance implications because they involve creating and destroying objects on the heap, which can be slower than working with value types directly. Therefore, it's generally recommended to minimize boxing and unboxing in performance-critical code.