---
title: "name of Pandas library tools used to create a scatter plot matrix?"
datePublished: Thu Mar 09 2023 08:17:25 GMT+0000 (Coordinated Universal Time)
cuid: clf0u5xa300000ajy9wma683x
slug: name-of-pandas-library-tools-used-to-create-a-scatter-plot-matrix
tags: name-of-pandas-library-tools-used-to-create-a-scatter-plot-matrix

---

The Pandas library provides a function called `scatter_matrix()` in the `pandas.plotting` a module that can be used to create a scatter plot matrix. The `scatter_matrix()` the function takes a data frame as its first argument and generates a matrix of scatter plots that show the pairwise relationships between all pairs of variables in the data frame. Each scatter plot in the matrix shows the relationship between two variables, with one variable plotted on the x-axis and the other variable plotted on the y-axis.

Here's an example of using the `scatter_matrix()` function to create a scatter plot matrix:

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

# create a DataFrame
data = {'x': np.random.randn(100),
        'y': np.random.randn(100),
        'z': np.random.randn(100)}
df = pd.DataFrame(data)

# create a scatter plot matrix
pd.plotting.scatter_matrix(df, alpha=0.5, figsize=(8,8))

plt.show()
```

Output:

![scatter plot matrix](https://i.imgur.com/z2NU4Lu.png align="left")

In the above example, we first created a data frame with three variables `x`, `y`, and `z`. We then passed this data frame to the `scatter_matrix()` function in the `pandas.plotting` module to create a scatter plot matrix. The `alpha` argument is used to set the transparency of the points, and the `figsize` argument is used to set the size of the figure. Finally, we displayed the scatter plot matrix using the `show()` method of the `plt` module in Matplotlib.