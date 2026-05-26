# 在Pandas中对指定列进行渐变颜色映射

> 原文：[https://www.geeksforgeeks.org/make-a-gradient-color-mapping-on-a-specified-column-in-pandas/](https://www.geeksforgeeks.org/make-a-gradient-color-mapping-on-a-specified-column-in-pandas/)

让我们看看如何在Pandas数据帧的特定列上进行渐变颜色映射。我们可以使用`Styler`类的`Styler.background_gradient()`函数来实现。

> **语法**：`styler.background_gradient(cmap='PuBu', low=0, high=0, axis=0, subset=None)`
>
> **参数：**
>
> `cmap`：str 或 colormap (matplotlib colormap)
>
> `low`, `high`：float (用这些值压缩范围。)
>
> `axis`：int 或 str (1 或 'columns' 表示按列，0 或 'index' 表示按行)
>
> `subset`：IndexSlice (将样式应用限制到的有效数据切片)
>
> **返回**：self

**进场：**

*   导入pandas模块
*   创建数据帧
*   使用`style.background_gradient()`函数明智地选择特定列
*   显示数据帧

让我们用例子来理解：

## 例1

创建一个数据框并渐变所有列。

```python
# importing pandas module
import pandas as pd

# Creating pandas DataFrame
df = pd.DataFrame({"A": [1, 2, -3, 4, -5, 6],
                   "B": [3, -5, -6, 7, 3, -2],
                   "C": [-4, 5, 6, -7, 5, 4],
                   "D": [34, 5, 32, -3, -56, -54]})

# Displaying the original DataFrame
print("Original Array : ")
print(df)

# backgroung color mapping
print("\nDataframe - Gradient color:")
df.style.background_gradient()
```

**输出：**

![](img/02bd33a689439234173f1a7d15c59579.png)

## 例2

创建一个数据框，并对特定的列进行渐变。

```python
# importing pandas module
import pandas as pd

# Creating pandas DataFrame
df = pd.DataFrame({"A": [1, 2, -3, 4, -5, 6],
                   "B": [3, -5, -6, 7, 3, -2],
                   "C": [-4, 5, 6, -7, 5, 4],
                   "D": [34, 5, 32, -3, -56, -54]})

# Displaying the original DataFrame
print("Original Array : ")
print(df)

# backgroung color mapping
print("\nDataframe - Gradient color:")

# df.style.background_gradient()
df.style.background_gradient(subset='B')
```

**输出：**

![](img/5a4ced35c9eeb3146d4f02a06001e15a.png)

如果您想更改另一列：

```python
df.style.background_gradient(subset='D')
```

**输出：**

![](img/93ed94aa2026f5173ca1598129618b0d.png)