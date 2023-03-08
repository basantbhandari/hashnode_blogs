---
title: "generate a random number in c# with an example"
datePublished: Wed Mar 08 2023 07:24:40 GMT+0000 (Coordinated Universal Time)
cuid: clezcu890000209mogouigvj2
slug: generate-a-random-number-in-c-with-an-example
tags: generate-a-random-number-in-c-with-an-example

---

here's an example of how to generate a random number in C# using the `Random` class:

```csharp
using System;

class Program {
    static void Main(string[] args) {
        // Create a new instance of the Random class
        Random random = new Random();

        // Generate a random integer between 1 and 100 (inclusive)
        int randomNumber = random.Next(1, 101);

        // Print the random number to the console
        Console.WriteLine("Random number: " + randomNumber);
    }
}
```

In this example, we first create a new instance of the `Random` class using the `new` keyword. We then use the `Next` method of the `Random` class to generate a random integer between 1 and 100 (inclusive). Finally, we print the random number to the console using the `Console.WriteLine` method. Note that each time you run this code, you will get a different random number.