# 如何从字符串列表中检查 Pandas 列是否有值？

> 原文: [https://www.geeksforgeeks.org/how-to-check-if-pandas-column-has-value-from-list-of-string/](https://www.geeksforgeeks.org/how-to-check-if-pandas-column-has-value-from-list-of-string/)

在本文中，我们将看到如何在 Python 中检查 pandas 列是否具有字符串列表中的值。

字符串列表意味着列表包含字符串作为元素，我们将检查 pandas dataframe 是否具有字符串列表中的值，并在它们存在时显示它们。我们将获取列表中字符串包含的 dataframe 列。

## 创建示例数据帧

```py
#import pandas
import pandas

# create dataframe
data = pandas.DataFrame({'name': ['sireesha', 'priyank', 
                                  'ojaswi', 'gnanesh'], 
                         'subjects': ['java', 'networks',
                                      'c', 'c#']})

# display
data
```

**输出:**

![](img/5dfd23407639dd6da8dd21d39cf5afc4.png)

## 方法一: 使用 `isin()` 功能

在这种情况下，`isin()` 函数检查包含列表中出现的字符串的 pandas 列，并在出现列值时返回列值，否则它将不会选择 dataframe 列。

> **语法**: `dataframe[dataframe['column_name'].isin(list_of_strings)]`
>
> 其中
>
> *   `dataframe` 是输入数据帧
> *   `list_of_strings` 是包含字符串的列表
> *   `column_name` 是用于检查该列中字符串列表的列

**示例**: Python 程序，用于检查 pandas 列是否具有字符串列表中的值

```py
#import pandas
import pandas

# create dataframe
data = pandas.DataFrame({'name': ['sireesha', 'priyank',
                                  'ojaswi', 'gnanesh'],
                         'subjects': ['java', 'networks',
                                      'c', 'c#']})

# consider a list
list1 = ['sireesha', 'priyank']

# check the pandas name column
# contain the given list if strings
print(data[data['name'].isin(list1)])

# consider a list
list2 = ['java', 'c']

# check the pandas subjects column
# contain the given list if strings
print(data[data['subjects'].isin(list2)])
```

**输出:**

![](img/0f744a2de7d801cbe6b9404dc7c4dcb8.png)

## 方法二: 使用 `NumPy`

这里，`NumPy` 还使用 `isin()` 运算符来检查 pandas 列是否具有字符串列表中的值。

> **语法**: `dataframe[~numpy.isin(dataframe['column'], list_of_values)]`

**示例:**

```py
# import pandas
import pandas

# import numpy
import numpy

# create dataframe
data = pandas.DataFrame({'name': ['sireesha', 'priyank',
                                  'ojaswi', 'gnanesh'], 
                         'subjects': ['java', 'networks', 
                                      'c', 'c#']})

# consider a list
list1 = ['sireesha', 'priyank']

# check the pandas name column
# contain the given list if strings
print(data[data['name'].isin(list1)])

# consider a list
list2 = ['java', 'c']

# check the pandas subjects column
# contain the given list if strings
data[~numpy.isin(data['subjects'], list1)]
```

**输出:**

![](img/e449a4cf2ee88f796a52dc4b9d46421d.png)