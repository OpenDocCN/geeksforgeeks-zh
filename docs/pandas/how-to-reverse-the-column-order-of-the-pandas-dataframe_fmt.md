# 如何反转熊猫数据框的列顺序？

> 原文: [https://www.geeksforgeeks.org/how-to-reverse-the-column-order-of-the-pandas-dataframe/](https://www.geeksforgeeks.org/how-to-reverse-the-column-order-of-the-pandas-dataframe/)

有时在处理数据帧时，我们可能希望更改或颠倒数据帧的列顺序。在本文中，让我们看看如何反转数据框的列顺序。这可以通过两种方式实现–

## 方法 1

通过使用`dataframe.columns[::-1]`属性，可以颠倒数据框中出现的列的顺序。它从末尾访问列，外部数据框`[...]`使用提供的新序列重新索引数据框。

**示例:**

```py
# importing required modules
import pandas as pd

dataframe = pd.DataFrame([[1, 'A', "Student"],
                          [2, 'B', "Tutor"],
                          [3, 'C', "Instructor"]])

print("Original DataFrame")
display(dataframe)

# reversing the dataframe
print("Reversed DataFrame")
display(dataframe[dataframe.columns[::-1]])
```

**输出:**

![](img/291e82e4183bc8079f35580b3d385ccb.png)

## 方法 2

`iloc`索引器也可用于反转数据框的列顺序，在指定的数据框上使用语法`dataframe.iloc[:, ::-1]`。内容不会保留在原始数据帧中。

```py
# importing required modules
import pandas as pd

dataframe = pd.DataFrame([[1, 'A', "Student"],
                          [2, 'B', "Tutor"],
                          [3, 'C', "Instructor"]])

print("Original DataFrame")
display(dataframe)

# reversing the dataframe
print("Reversed DataFrame")
display(dataframe.iloc[:, ::-1])
```

**输出:**

![](img/9e46a6b7b06ffa86d5b75e9f706fa47b.png)