# 将熊猫数据帧导出到JSON文件

> 原文：[https://www.geeksforgeeks.org/exporting-pandas-dataframe-to-json-file/](https://www.geeksforgeeks.org/exporting-pandas-dataframe-to-json-file/)

让我们看看如何将熊猫数据帧导出为JSON文件。为了执行这个任务，我们将使用`DataFrame.to_json()`和`pandas.read_json()`函数。

**例1：**

## 蟒3

```py
# importing the module
import pandas as pd

# creating a DataFrame
df = pd.DataFrame([['a', 'b', 'c'], ['d', 'e', 'f'], ['g', 'h', 'i']],
                  index =['row 1', 'row 2', 'row3'],
                  columns =['col 1', 'col 2', 'col3'])

# storing the data in JSON format
df.to_json('file.json', orient = 'split', compression = 'infer', index = 'true')

# reading the JSON file
df = pd.read_json('file.json', orient ='split', compression = 'infer')

# displaying the DataFrame
print(df)
```