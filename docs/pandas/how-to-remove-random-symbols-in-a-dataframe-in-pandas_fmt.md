# 如何去除熊猫数据框中的随机符号？

> 原文: [https://www.geeksforgeeks.org/how-to-remove-random-symbols-in-a-dataframe-in-pandas/](https://www.geeksforgeeks.org/how-to-remove-random-symbols-in-a-dataframe-in-pandas/)

在本文中，我们将看到如何删除熊猫数据框中的随机符号。

## 方法一：选列

> **语法:** `DataFrame[column].replace({symbol: ''}, regex=True)`

首先，选择需要删除符号的列。并在 `replace()` 方法中插入符号示例 `replace("h":"")`。

### 蟒蛇 3

```py
import pandas as pd

df = pd.DataFrame({'A': [1, 2, 3],
                   'B': [4, 5, 6],
                   'C': ['f;', 'd:', 'sda;sd'],
                   'D': ['s', 'd;', 'd;p'],
                   'E': [5, 3, 6],
                   'F': [7, 4, 3]})

print(df)

cols_to_check = ['C', 'D', 'E']
print(df[cols_to_check])

df[cols_to_check] = df[cols_to_check].replace({';': ''}, regex=True)
print(df)
```

**输出:**

![](img/28ab72347548e6a9b753382637fbf883.png)

## 方法二：使用 `DataFrame.iloc[]`

> **语法:**
>
> `dataframe.iloc[].replace({character}, regex=True)`

在这种方法中，您可以使用 `dataframe.iloc[]` 来更改符号。

### 蟒蛇 3

```py
import pandas as pd

df = pd.DataFrame({'A': [1, 2, 3],
                   'B': [4, 5, 6],
                   'C': ['f;', 'd:', 'sda;sd'],
                   'D': ['s', 'd;', 'd;p'],
                   'E': [5, 3, 6],
                   'F': [7, 4, 3]})

print(df)

cols_to_check = ['C', 'D', 'E']
print(df.iloc[[0, 2]])

df.iloc[[0, 2]] = df.iloc[[0, 2]].replace({';': ''}, regex=True)
print(df)
```

**输出:**

![](img/8e9ec6aa254834fff0bbfc836034b803.png)

## 方法三：使用 `DataFrame.loc[]`

> **语法:**
>
> `dataframe.loc[].replace({character}, regex=True)`

### 蟒蛇 3

```py
import pandas as pd

df = pd.DataFrame({'A': [1, 2, 3],
                   'B': [4, 5, 6],
                   'C': ['f;', 'd:', 'sda;sd'],
                   'D': ['s', 'd;', 'd;p'],
                   'E': [5, 3, 6],
                   'F': [7, 4, 3]})

print(df)

cols_to_check = ['C', 'D', 'E']
print(df.loc[:, cols_to_check])

df.loc[:, cols_to_check] = df.loc[
  :, cols_to_check].replace({';': ''}, regex=True)
print(df)
```

**输出:**

![](img/41dc6b18cbf6b3942c6cbc517f6a5864.png)