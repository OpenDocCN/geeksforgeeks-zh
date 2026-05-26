# 使用 Python 中的 Pandas 创建并显示一维数组状对象

> 原文: [https://www.geeksforgeeks.org/create-and-display-a-one-dimensional-array-like-object-using-pandas-in-python/](https://www.geeksforgeeks.org/create-and-display-a-one-dimensional-array-like-object-using-pandas-in-python/)

`Series()` 是 Pandas 库中存在的一个函数，它创建一个一维数组，并且可以在其中保存任何类型的对象或数据。在本文中，让我们学习语法，使用 Pandas 库创建和显示包含数据数组的一维数组状对象。

## `Pandas.Series()`

> **语法:** `pandas.Series(参数)`
>
> **参数:**
>
> - `data`: 包含存储在序列中的数据。
> - `index`: 值必须是可散列的，并且具有与 `data` 相同的长度。
> - `dtype`: 输出序列的数据类型。
> - `name`: 给予系列的名称。
> - `copy`: 复制输入数据。
>
> **返回:** `Series` 类的一个对象

**示例 1:** 从列表创建系列

```py
# import the library
import pandas as pd

# create the one-dimensional array
data = [1, 2, 3, 4, 5]

# create the Series
ex1 = pd.Series(data)

# displaying the Series
print(ex1)
```

**输出:**
![](img/e41b9615cb0ddb9dda84b957f1abf141.png)

**示例 2:** 从 NumPy 数组创建系列。

```py
# import the pandas and numpy library
import pandas as pd
import numpy as np

# create numpy array
data = np.array(['a', 'b', 'c', 'd'])

# create one-dimensional data
s = pd.Series(data)

# display the Series
print(s)
```

**输出:**
![](img/cbf715e52d02cb70cfa504d4038a4b5a.png)

**示例 3:** 从字典创建系列。

```py
# import the pandas library
import pandas as pd

# create dictionary
dict = {'a' : 0.1, 'b' : 0.2, 'c' : 0.3}

# create one-dimensional data
s = pd.Series(dict)

# display the Series
print(s)
```

**输出:**
![](img/fbbe45e433e5f293c1dadb7bf47d834a.png)

**示例 4:** 从列表列表创建系列。

```py
# importing the module
import pandas as pd

# creating the data
data = [['g', 'e', 'e', 'k', 's'],
        ['f', 'o', 'r'],
        ['g', 'e', 'e', 'k', 's']]

# creating a Pandas series of lists
s = pd.Series(data)

# displaying the Series
print(s)
```

**输出:**
![](img/9ce1d80acd46e082f335d416b665233d.png)