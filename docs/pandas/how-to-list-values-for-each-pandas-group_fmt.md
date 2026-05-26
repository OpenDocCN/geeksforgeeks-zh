# 如何列出每个熊猫组的值？

> 原文：[https://www.geeksforgeeks.org/how-to-list-values-for-each-pandas-group/](https://www.geeksforgeeks.org/how-to-list-values-for-each-pandas-group/)

在本文中，我们将看到如何显示`数据框`所在的每个`组`的所有值。首先使用`DataFrame.groupby()`方法将`数据帧`分成`组`。然后我们修改它，使每个`组`包含列表中的值。

首先，让我们创建一个`数据框`：

## Python 3

```py
# import pandas library
import pandas as pd

# create a dataframe
df = pd.DataFrame({'a': ['A', 'A', 'B',
                         'B', 'B', 'C',
                         'C', 'D'], 
                   'b': [1, 2, 5,
                         3, 5, 4,
                         8, 6]})
# show the dataframe                  
df
```