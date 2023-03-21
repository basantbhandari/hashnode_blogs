---
title: "circular import in python"
datePublished: Tue Mar 21 2023 14:59:11 GMT+0000 (Coordinated Universal Time)
cuid: clfidstj400000aju8ddh4iri
slug: circular-import-in-python
tags: circular-import-in-python

---

Circular imports occur in Python when two or more modules depend on each other, directly or indirectly. This creates a situation where Python is unable to determine the order in which the modules should be loaded, and it results in a circular dependency. Here is an example:

```python
# module_a.py
import module_b

def function_a():
    print("Hello from function_a in module_a")
    module_b.function_b()

# module_b.py
import module_a

def function_b():
    print("Hello from function_b in module_b")
    module_a.function_a()
```

In the above example, module\_a depends on module\_b and module\_b depends on module\_a. This creates a circular dependency between the two modules. When Python tries to load either of the modules, it gets stuck in an infinite loop.

To avoid circular imports, you can refactor your code to remove the circular dependency. One way to do this is by moving the shared functionality between the modules into a third module that both modules can import. Alternatively, you can import a module only where you need it instead of importing it at the top of the file.

For example, in the above code, you can move the shared functionality into a third module, like this:

```python
# module_shared.py

def shared_function():
    print("Hello from shared_function")

# module_a.py
import module_shared

def function_a():
    print("Hello from function_a in module_a")
    module_shared.shared_function()

# module_b.py
import module_shared

def function_b():
    print("Hello from function_b in module_b")
    module_shared.shared_function()
```

In this refactored code, the shared functionality is moved to the module\_shared module. Both module\_a and module\_b import this module to access the shared functionality, thus removing the circular dependency.