# 突出熊猫中每一列的最大值

> 原文: [https://www.geeksforgeeks.org/highlight-the-maximum-value-in-each-column-in-pandas/](https://www.geeksforgeeks.org/highlight-the-maximum-value-in-each-column-in-pandas/)

让我们讨论如何突出`pandas`数据框中的最大值。让我们首先制作一个数据帧：

## 例：

## 蟒3

```py
# Import Required Libraries
import pandas as pd
import numpy as np

# Create a dictionary for the dataframe
dict = {'Name': ['Sukritin', 'Sumit Tyagi', 'Akriti Goel',
                 'Sanskriti', 'Abhishek Jain'], 
        'Age': [22, 20, 45, 21, 22],
        'Marks': [90, 84, 33, 87, 82]}

# Converting Dictionary to Pandas Dataframe
df = pd.DataFrame(dict)

# Print Dataframe
df
```