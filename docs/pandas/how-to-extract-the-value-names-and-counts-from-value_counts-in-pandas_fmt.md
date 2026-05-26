# 如何从Pandas中的`value_counts()`中提取值名和计数？

> 原文：[https://www.geeksforgeeks.org/how-to-extract-the-value-names-and-counts-from-value_counts-in-pandas/](https://www.geeksforgeeks.org/how-to-extract-the-value-names-and-counts-from-value_counts-in-pandas/)

## 先决条件

*   [Pandas](https://www.geeksforgeeks.org/pandas-tutorial/)
*   [Matplotlib](https://www.geeksforgeeks.org/python-introduction-matplotlib/)

在本文中，我们将学习如何使用`value_counts()`从Pandas中提取名称和值。Pandas库配备了许多有用的功能，`value_counts`就是其中之一。该函数返回Pandas数据帧中唯一项目的计数。

## 语法

> `<object>.value_counts()`

## 进场

*   导入必需模块。
*   制作数据框。
*   使用`value_counts()`进行处理。
*   显示数据。

### 示例1：打印列表中所有唯一的国家和第一个国家名称

> `tolist()`函数返回一个值列表。
> 
> **语法：** `Index.tolist()`
> **参数：** None
> **返回：** 列表

```python
import pandas as pd
import matplotlib.pyplot as plt

# Make example dataframe
df = pd.DataFrame([(1, 'Germany'),
                   (2, 'France'),
                   (3, 'Indonesia'),
                   (4, 'France'),
                   (5, 'France'),
                   (6, 'Germany'),
                   (7, 'UK'),
                   (8, 'India'),
                   (9, 'India'),
                   (10, 'Germany')
                   ],
                  columns=['groupid', 'country'],
                  index=['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j'])

# print all unique country name in the list
su1 = df['country'].value_counts().index.tolist()
print(su1)

# print 1st unique country name present in a list
su2 = df['country'].value_counts().index.tolist()[0]
print(su2)
```

**输出：**

![](img/64cb1bba15e8bb743a10519f9052efa8.png)

### 示例2：打印该列的所有唯一值和该列的第一个值

> `value_counts()`统计列中值的唯一出现次数。
> 
> **语法：** `Index.value_counts()`
> **参数：**
> **返回：** 该列中每个唯一值的出现次数。

```python
import pandas as pd
import matplotlib.pyplot as plt

# Make example dataframe
df = pd.DataFrame([(1, 'Germany'),
                   (2, 'France'),
                   (3, 'Indonesia'),
                   (4, 'France'),
                   (5, 'France'),
                   (6, 'Germany'),
                   (7, 'UK'),
                   (8, 'India'),
                   (9, 'India'),
                   (10, 'Germany')
                   ],
                  columns=['groupid', 'country'],
                  index=['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j'])

# print country name and counts
su3 = df['country'].value_counts()
print(su3)

# print 1st country count in a list
su4 = df['country'].value_counts()[0]
print(su4)
```

**输出：**

![](img/9eeeedafcca8d9d9a35ce59bf576eff2.png)

### 示例3：使用列表中的循环打印我们的数据

```python
import pandas as pd
import matplotlib.pyplot as plt

# Make example dataframe
df = pd.DataFrame([(1, 'Germany'),
                   (2, 'France'),
                   (3, 'Indonesia'),
                   (4, 'France'),
                   (5, 'France'),
                   (6, 'Germany'),
                   (7, 'UK'),
                   (8, 'India'),
                   (9, 'India'),
                   (10, 'Germany')
                   ],
                  columns=['groupid', 'country'],
                  index=['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j'])

# printing names and count using loop.
for idx, name in enumerate(df['country'].value_counts().index.tolist()):
    print('Name :', name)
    print('Counts :', df['country'].value_counts()[idx])
```

**输出：**

![](img/17f1c22cc737b723d589689322ae5cf4.png)

### 示例4：以条形图的形式打印我们的数据

> **语法：** `matplotlib.pyplot.plot(kind=' ')`
> **参数：** `kind`：图的类型，即`line`、`bar`。
> **返回：** 返回图形。

```python
import pandas as pd
import matplotlib.pyplot as plt

# Make example dataframe
df = pd.DataFrame([(1, 'Germany'),
                   (2, 'France'),
                   (3, 'Indonesia'),
                   (4, 'France'),
                   (5, 'France'),
                   (6, 'Germany'),
                   (7, 'UK'),
                   (8, 'India'),
                   (9, 'India'),
                   (10, 'Germany')
                   ],
                  columns=['groupid', 'country'],
                  index=['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j'])

# Display data in a form of Graph
df['country'].value_counts().plot(kind='bar')
plt.show()
```

**输出：**

![](img/245e0c3d030a968df4d9d5f9ceaa00c4.png)