# 熊猫-蟒蛇中一列的对数和自然对数值

> 原文: [https://www.geeksforgeeks.org/log-and-natural-logarithmic-value-of-a-column-in-pandas-python/](https://www.geeksforgeeks.org/log-and-natural-logarithmic-value-of-a-column-in-pandas-python/)

熊猫中一列的对数和自然对数值可以分别使用`log()`、`log2()`和`log10()` `numpy`函数计算。在应用函数之前，我们需要创建一个数据帧。

## 蟒 3

```py
# Import required libraries
import pandas as pd
import numpy as np

# Dictionary
data = {
     'Name': ['Geek1', 'Geek2',
              'Geek3', 'Geek4'],
   'Salary': [18000, 20000, 
              15000, 35000]}

# Create a dataframe
data = pd.DataFrame(data,
                    columns = ['Name', 
                               'Salary'])

# Show the dataframe
data
```