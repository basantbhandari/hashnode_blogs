---
title: "docstring in Python?"
datePublished: Sat Mar 11 2023 16:28:38 GMT+0000 (Coordinated Universal Time)
cuid: clf46lbeq000k09lafxil6fwr
slug: docstring-in-python
tags: docstring-in-python

---

In Python, a docstring is a string literal that is used to document a module, function, class, or method. Docstrings are placed immediately after the definition of the entity they document and are enclosed in triple quotes (either single or double).

There are two main styles of docstrings: the one-line docstring and the multi-line docstring.

The one-line docstring is a brief summary of the entity being documented and is used for simple functions or methods. It is enclosed in triple quotes on a single line, like this:

```python
pythonCopy codedef my_function():
    """This function does something."""
    # function body goes here
```

The multi-line docstring is used for more complex entities, and includes a more detailed description of the entity, as well as information about its parameters, return value, and any exceptions it may raise. The multi-line docstring is enclosed in triple quotes and spans multiple lines, like this:

```python
pythonCopy codedef my_function(param1, param2):
    """
    This function does something.

    Parameters:
    param1 (int): The first parameter.
    param2 (str): The second parameter.

    Returns:
    str: The result of the function.
    """
    # function body goes here
```

Note that the first line of a multi-line docstring should be a brief summary of the entity being documented, followed by a blank line, and then any additional information about the entity. The additional information is typically organized into sections, such as "Parameters", "Returns", and "Raises".

Using docstrings is a good programming practice because it helps to document your code, making it easier to understand and maintain. Docstrings can be accessed using the built-in `help()` function or through various documentation generation tools.