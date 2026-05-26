# 使用列表创建熊猫数据帧

> 原文：[https://www.geeksforgeeks.org/creating-pandas-dataframe-using-list-of-lists/](https://www.geeksforgeeks.org/creating-pandas-dataframe-using-list-of-lists/)

Pandas DataFrame 是一个二维标记数据结构，具有潜在的不同类型的列。它通常是 Pandas 中最常用的对象。
熊猫数据框可以通过多种方式创建。让我们讨论如何使用列表的列表来创建熊猫数据帧。

## 代码#1

```py
# Import pandas library
import pandas as pd

# initialize list of lists
data = [['Geeks', 10], ['for', 15], ['geeks', 20]]

# Create the pandas DataFrame
df = pd.DataFrame(data, columns = ['Name', 'Age'])

# print dataframe.
print(df)
```

**输出：**

```py
Name  Age
0  Geeks   10
1    for   15
2  geeks   20
```