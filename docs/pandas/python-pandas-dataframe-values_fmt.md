# Pandas DataFrame.values属性

> 原文: [https://www.geeksforgeeks.org/python-pandas-dataframe-values/](https://www.geeksforgeeks.org/python-pandas-dataframe-values/)

## 介绍
Pandas `DataFrame`是一个二维可变大小、潜在异构的表格数据结构，带有标记轴（行和列）。算术运算在行标签和列标签上对齐。它可以被认为是`Series`对象的类似字典的容器。这是Pandas的主要数据结构。

Pandas `DataFrame.values`属性返回给定数据帧的`numpy`表示。

## 语法
`语法:` `DataFrame.values`
`参数:` 无
`返回:` `numpy.ndarray`

## 示例

### 示例 1
使用`DataFrame.values`属性返回给定数据帧的`numpy`表示。

```py
# importing pandas as pd
import pandas as pd

# Creating the DataFrame
df = pd.DataFrame({'Weight':[45, 88, 56, 15, 71],
                   'Name':['Sam', 'Andrea', 'Alex', 'Robin', 'Kia'],
                   'Age':[14, 25, 55, 8, 21]})

# Print the DataFrame
print(df)
```

**输出:**
![](img/1356f90288db4c37b433b87455a29dd6.png)

现在我们将使用`DataFrame.values`属性返回给定数据帧的`numpy`表示。

```py
# return the numpy representation of this dataframe
result = df.values

# Print the result
print(result)
```

**输出:**
![](img/50ea1b507c7e0419e7a01226fa71957e.png)

正如我们在输出中看到的那样，`DataFrame.values`属性已经成功地返回了给定数据帧的`numpy`表示。

### 示例 2
使用`DataFrame.values`属性返回给定数据帧的`numpy`表示。

```py
# importing pandas as pd
import pandas as pd

# Creating the DataFrame
df = pd.DataFrame({"A":[12, 4, 5, None, 1], 
                   "B":[7, 2, 54, 3, None], 
                   "C":[20, 16, 11, 3, 8], 
                   "D":[14, 3, None, 2, 6]})

# Print the DataFrame
print(df)
```

**输出:**
![](img/d4d2449c30c54e3783c9ef9486e03dd6.png)

现在我们将使用`DataFrame.values`属性返回给定数据帧的`numpy`表示。

```py
# return the numpy representation of this dataframe
result = df.values

# Print the result
print(result)
```

**输出:**
![](img/16243e73d9de93f616344606dfea400b.png)

正如我们在输出中看到的那样，`DataFrame.values`属性已经成功地返回了给定数据帧的`numpy`表示。