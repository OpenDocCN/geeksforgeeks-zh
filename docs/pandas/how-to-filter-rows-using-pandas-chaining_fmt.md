# 如何使用熊猫链过滤行？

> 原文：[https://www.geeksforgeeks.org/how-to-filter-rows-using-pandas-chaining/](https://www.geeksforgeeks.org/how-to-filter-rows-using-pandas-chaining/)

在本文中，我们将学习如何使用熊猫链接来过滤行。为此，我们首先研究了下面给出的一些以前的术语：

*   `Pandas DataFrame`：它是一个二维数据结构，即数据按行和列对齐。`Pandas DataFrame`有三个主要组成部分，即数据、行和列。
*   `Pandas`链：方法链，即逐个调用对象上的方法。这一直是`Pandas`中一种可能的编程风格。在过去几个版本中，引入了许多允许更多链接的方法。

这里，我们使用`Pandas`中的链接概念来过滤数据帧，并获得与输出相同的行。这很容易通过例子来解释。这里我们使用一个数据框架，它由如下所示的人的一些数据组成：

## Python

```py
# import package
import pandas as pd

# define data
data = pd.DataFrame(
  {'ID': {0: 105, 1: 102, 2: 101, 3: 106, 4: 103, 5: 104, 6: 107},

'Name': {0: 'Ram Kumar', 1: 'Jack Wills', 2: 'Deepanshu Rustagi', 
          3: 'Thomas James', 4: 'Jenny Advekar', 5: 'Yash Raj', 
          6: 'Raman Dutt Mishra'},

'Age': {0: 40, 1: 23, 2: 20, 3: 34, 4: 18, 5: 56, 6: 35},

'Country': {0: 'India', 1: 'Uk', 2: 'India', 3: 'Australia', 
               4: 'Uk', 5: 'India', 6: 'India'}
  }
)

# view data
data
```