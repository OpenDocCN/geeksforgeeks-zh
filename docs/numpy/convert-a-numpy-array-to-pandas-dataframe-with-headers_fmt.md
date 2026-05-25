# 将 NumPy 数组转换为带有标题的熊猫数据帧

> 原文：[https://www.geeksforgeeks.org/convert-a-numpy-array-to-pandas-dataframe-with-headers/](https://www.geeksforgeeks.org/convert-a-numpy-array-to-pandas-dataframe-with-headers/)

要将 numpy 数组转换为熊猫数据帧，我们使用 `pandas.DataFrame()` 的功能。

> **语法：** `pandas.DataFrame(data=None, index=None, columns=None)`
>
> **参数：**
> `data`：`numpy.ndarray`，`dict` 或 `dataframe`
> `index`：结果数据帧的索引
> `columns`：结果数据帧的列标签

## 示例 1

```py
import numpy as np
import pandas as pd

arr = np.random.rand(4, 3)
print("Numpy array:")
print(arr)

# convert numpy array to dataframe
df = pd.DataFrame(arr, columns =['A', 'B', 'C'])
print("\nPandas DataFrame: ")
df
```

**输出：**

![numpy-array-to-dataframe-1](img/763d8841f3c2c6e9fc432dd82bab3c52.png)

## 示例 2

```py
import numpy as np
import pandas as pd

arr = np.random.rand(6).reshape(2, 3)
print("Numpy array:")
print(arr)

# convert numpy array to dataframe
df = pd.DataFrame(arr, columns =['C1', 'C2', 'C3'])
print("\nPandas DataFrame: ")
df
```

**输出：**

![numpy-araay-to-dataframe-2](img/94cc80bb6c9e35580e9f0a0550dc9fe4.png)

## 示例 3

```py
import numpy as np
import pandas as pd

arr = np.array([[1, 2], [4, 5]])
print("Numpy array:")
print(arr)

# convert numpy array to dataframe
df = pd.DataFrame(data = arr, index =["row1", "row2"], 
                  columns =["col1", "col2"])

print("\nPandas DataFrame: ")
df
```

**输出：**

![numpy-array-to-dataframe-3](img/69d1ef277268b7b527abf2790be9fba5.png)