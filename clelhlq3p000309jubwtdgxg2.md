# what are nullable types in c#

In C#, a nullable type is a value type that can also have a null value. Normally, value types (such as `int`, `bool`, `double`, etc.) cannot have a null value, but nullable types provide a way to represent them as null when needed.

Nullable types in C# are represented using the `?` character after the value type name. For example, `int?` is a nullable integer type, `bool?` a nullable boolean type, and so on.

To assign a null value to a nullable type variable, you can use the `null` keyword. For example:

```csharp
int? nullableInt = null;
bool? nullableBool = null;
```

You can check whether a nullable value has a value or is null using the `HasValue` property, and access its value using the `Value` property. However, accessing the `Value` property when the nullable value is null will result in a `System.InvalidOperationException`.

```csharp
if (nullableInt.HasValue)
{
    int value = nullableInt.Value;
}
```

Nullable types are useful in scenarios where you need to represent missing data or the absence of a value. They can be used with database queries, LINQ queries, and other situations where you might need to work with nullable values.

Note that nullable types were introduced in C# 2.0 and are not available in all .NET languages.