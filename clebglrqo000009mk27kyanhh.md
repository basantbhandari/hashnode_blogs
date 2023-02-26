# SOLID design pattern with example in python?

SOLID is a set of design principles that help developers create maintainable and scalable software systems. The principles of SOLID are intended to guide developers in designing code that is flexible, robust, and easy to maintain. In this article, we will explore each of the five SOLID principles and provide an example in Python.

1. Single Responsibility Principle (SRP)
    

The Single Responsibility Principle states that a class should have only one reason to change. This means that a class should have only one responsibility, and if that responsibility changes, the class should change too. This principle encourages developers to write code that is focused and easy to understand.

Example:

Consider a Python class that calculates the area of a rectangle. The class would have only one responsibility, which is to calculate the area of a rectangle.

```python
class Rectangle:
    def __init__(self, width, height):
        self.width = width
        self.height = height

    def area(self):
        return self.width * self.height
```

1. Open/Closed Principle (OCP)
    

The Open/Closed Principle states that software entities (classes, modules, functions) should be open for extension but closed for modification. This means that developers should be able to add new functionality to a system without changing the existing code. This principle encourages developers to write code that is modular and easy to extend.

Example:

Consider a Python class that performs operations on a list of numbers. The class can be extended to add new operations without modifying the existing code.

```python
class NumberOperations:
    def __init__(self, numbers):
        self.numbers = numbers

    def sum(self):
        return sum(self.numbers)

    def average(self):
        return sum(self.numbers) / len(self.numbers)
```

1. Liskov Substitution Principle (LSP)
    

The Liskov Substitution Principle states that subtypes should be substitutable for their base types. This means that a class should be able to substitute its base class without changing the behavior of the system. This principle encourages developers to write code that is flexible and can be extended easily.

Example:

Consider a Python class hierarchy that models different types of birds. Each bird class can implement a common method `fly()`, which can be substituted with the base bird class.

```python
class Bird:
    def fly(self):
        raise NotImplementedError

class Eagle(Bird):
    def fly(self):
        return "Soaring in the sky"

class Penguin(Bird):
    def fly(self):
        return "I can't fly!"
```

1. Interface Segregation Principle (ISP)
    

The Interface Segregation Principle states that clients should not be forced to depend on methods that they do not use. This means that an interface should be designed to be as small and focused as possible. This principle encourages developers to write code that is easy to understand and maintain.

Example:

Consider a Python interface that provides methods to read and write data. The interface can be separated into smaller interfaces to provide only the methods that are needed.

```python
class Readable:
    def read(self):
        raise NotImplementedError

class Writable:
    def write(self, data):
        raise NotImplementedError
```

1. Dependency Inversion Principle (DIP)
    

The Dependency Inversion Principle states that high-level modules should not depend on low-level modules. Instead, both should depend on abstractions. This means that code should be designed to depend on abstractions, not on concrete implementations. This principle encourages developers to write code that is modular and easy to change.

Example:

Consider a Python class that depends on a database implementation. The class can depend on an abstract interface instead of a concrete implementation, making it easier to switch to a different implementation.

```python
# Define an abstract interface for a database
class Database:
    def __init__(self):
        pass

    def save(self, data):
        raise NotImplementedError

    def load(self):
        raise NotImplementedError

# Define a high-level module that depends on the Database interface
class DataProcessor:
    def __init__(self, database):
        self.database = database

    def process_data(self, data):
        self.database.save(data)

# Define a low-level module that implements the Database interface
class SqliteDatabase(Database):
    def __init__(self):
        super().__init__()
        # Set up the connection to the database

    def save(self, data):
        # Save the data to the database

    def load(self):
        # Load the data from the database
```