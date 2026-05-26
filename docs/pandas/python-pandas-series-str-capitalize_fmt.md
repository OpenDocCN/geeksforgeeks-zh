# Python | Pandas Series.str.capitalize()

> 原文: [https://www.geeksforgeeks.org/python-pandas-series-str-capitalize/](https://www.geeksforgeeks.org/python-pandas-series-str-capitalize/)

`Series.str.capitalize()` 用于将 pandas Series 中的字符串元素大写。Series 是一种数据结构，在 Python 中与列表一样使用。Series 可以包含不同类型的数据，就像我们想在 Series 列表中输入的那样。

## 语法
`Series.str.capitalize()`

## 参数
无

## 返回
Series/Index 或 object

要获得 CSV 文件的链接，点击 [nba.csv](https://media.geeksforgeeks.org/wp-content/uploads/nba.csv)。

## 代码示例 #1
我们正在使用 pandas 的 `Series.str.capitalize()` 方法，该方法有助于将给定 Series 中每个字符串的第一个字母转换为大写字母，其余所有字符保持不变。

```py
import pandas as pd

data = pd.read_csv("nba.csv")

g = pd.Series(data['Name'].head())
print(g.str.lower(), end ='\n\n')
print(g.str.capitalize())
```

**输出：** 正如我们解释的，只有第一个字母应该被大写，其余的应该保持不变。你可以看到下面给出的输出。

```py
     Before

0    avery bradley
1      jae crowder
2     john holland
3      r.j. hunter
4    jonas jerebko
Name: Name, dtype: object

After

0    Avery bradley
1      Jae crowder
2     John holland
3      R.j. hunter
4    Jonas jerebko
Name: Name, dtype: object
```

## 代码示例 #2

```py
import pandas as pd

data = pd.read_csv("nba.csv")

g = pd.Series(data['Team'].head())
print(g.str.lower(), end ='\n\n')
print(g.str.capitalize())
```

**输出：**

```py
     Before

0    boston celtics
1    boston celtics
2    boston celtics
3    boston celtics
4    boston celtics
Name: Team, dtype: object

After

0    Boston celtics
1    Boston celtics
2    Boston celtics
3    Boston celtics
4    Boston celtics
Name: Team, dtype: object
```