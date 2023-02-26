# difference between out and ref parameters with valid c# example

Here's an example in C# that demonstrates the differences between `out` and `ref` parameters:

```csharp
csharpCopy codeclass Program
{
    static void Main(string[] args)
    {
        int x = 10;
        int y;

        // Using ref parameter
        AddFive(ref x);
        Console.WriteLine($"Value of x after AddFive(ref x): {x}"); // Output: Value of x after AddFive(ref x): 15

        // Using out parameter
        MultiplyByTen(2, out y);
        Console.WriteLine($"Value of y after MultiplyByTen(2, out y): {y}"); // Output: Value of y after MultiplyByTen(2, out y): 20
    }

    static void AddFive(ref int num)
    {
        num += 5;
    }

    static void MultiplyByTen(int num, out int result)
    {
        result = num * 10;
    }
}
```

In this example, we have a method `AddFive` takes a `ref` parameter `num` and adds 5 to its value. We also have a method `MultiplyByTen` that takes an `int` parameter `num` and an `out` parameter `result`. The method multiplies `num` by 10 and assigns the result to `result`.

In `Main`, we initialize the variable `x` with a value of 10, and then call `AddFive` with `x` as the argument. After the method call, we print the value of `x` to the console, which is now 15 because the `ref` parameter `num` was modified inside the `AddFive` method.

Next, we call `MultiplyByTen` with an argument of 2 for `num` and an `out` parameter `y`. After the method call, we print the value of `y` to the console, which is now 20 because the method assigned the result of multiplying `num` by 10 to `result`.

This example shows that while both `ref` and `out` parameters can modify the value of the parameter passed to the method, they are used in different situations. `ref` parameters are used when the method needs to modify the original value of the argument, while `out` parameters are used when the method needs to return a value of a different type or needs to return multiple values.