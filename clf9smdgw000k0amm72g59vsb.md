---
title: "python iterators?"
datePublished: Wed Mar 15 2023 14:44:09 GMT+0000 (Coordinated Universal Time)
cuid: clf9smdgw000k0amm72g59vsb
slug: python-iterators
tags: python-iterators

---

In Python, an iterator is an object that allows you to traverse a sequence or collection of elements one at a time, without the need to know the underlying structure of the collection. Iterators are implemented using the iterator protocol, which requires the iterator to have two methods: `__iter__()` and `__next__()`.

The `__iter__()` the method returns the iterator object itself, and the `__next__()` the method returns the next value in the sequence. When there are no more elements in the sequence, the `__next__()` method raises the `StopIteration` exception.

Here's an example of how to use iterators in Python:

```python
my_list = [1, 2, 3, 4, 5]

# Create an iterator object from the list
my_iter = iter(my_list)

# Print each element of the list using the iterator
print(next(my_iter))  # Output: 1
print(next(my_iter))  # Output: 2
print(next(my_iter))  # Output: 3
print(next(my_iter))  # Output: 4
print(next(my_iter))  # Output: 5

# When there are no more elements, the iterator raises StopIteration
print(next(my_iter))  # Raises StopIteration
```

In the example above, we first create an iterator object from the list using the `iter()` function. We then use the `next()` function to get each element of the list one at a time, until there are no more elements left.

In addition to built-in iterators like `range()`, Python also provides several other built-in functions and modules that use iterators, such as `map()`, `filter()`, and `zip()`. You can also define your own custom iterators using classes that implement the iterator protocol.