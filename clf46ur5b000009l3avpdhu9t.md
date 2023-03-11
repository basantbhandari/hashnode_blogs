---
title: "__init__? in python"
datePublished: Sat Mar 11 2023 16:35:58 GMT+0000 (Coordinated Universal Time)
cuid: clf46ur5b000009l3avpdhu9t
slug: init-in-python
tags: init

---

`__init__` is a special method in Python that is called when an object is created from a class. It is also known as a constructor method. The `__init__` the method is used to initialize the attributes of an object when it is created.

Here's an example:

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

person1 = Person("Alice", 25)
print(person1.name)
# Output: Alice

print(person1.age)
# Output: 25
```

In this example, we define a class called `Person` with an `__init__` method that takes two arguments, `name` and `age`. Inside the method, we set the `name` and `age` attributes of the object using the values passed in as arguments. We then create an instance of the `Person` class called `person1` with the name "Alice" and age 25, and print out the `name` and `age` attributes of the object.

The `self` parameter in the `__init__` method refers to the object that is being created. When we create an instance of the class (e.g., `person1`), Python automatically passes the instance as the first argument to the `__init__` method, so we don't need to pass it explicitly.

The `__init__` the method is an important method in Python classes, as it allows us to initialize the attributes of an object when it is created.