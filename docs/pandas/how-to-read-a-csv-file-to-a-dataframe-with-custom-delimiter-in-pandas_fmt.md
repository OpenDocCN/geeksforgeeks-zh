# 如何将 CSV 文件读入熊猫自定义分隔符的数据帧？

> 原文:[https://www . geesforgeks . org/how-read-a-CSV-file-to-a-data frame-带自定义分隔符的熊猫/](https://www.geeksforgeeks.org/how-to-read-a-csv-file-to-a-dataframe-with-custom-delimiter-in-pandas/)

由于以数据为中心的 Python 包的惊人生态系统，python 是进行数据分析的好语言。[`pandas`](https://www.geeksforgeeks.org/python-pandas-dataframe/)包就是其中之一，让导入和分析数据变得容易多了。
在这里，我们将讨论如何将 csv 文件加载到 `DataFrame` 中。这是用`read_csv()`方法完成的。我们要导入`pandas`库才能使用这个方法。

> **语法:**`pd.read_csv(file_path_or_buffer, sep=',', delimiter=None, header='infer', names=None, index_col=None, usecols=None, squeeze=False, prefix=None, mangle_dupe_cols=True, dtype=None, engine=None, converters=None, true_values=None, false_values=None, skipinitialspace=False, skiprows=None, nrows=None, na_values=None, keep_default_na, lineterminator=None, quotechar='"', quoting=0, escapechar=None, comment=None, encoding=None, dialect=None, tupleize_cols=None, error_bad_lines=True, warn_bad_lines=True, skipfooter=0, doublequote=True, delim_whitespace=False, low_memory=True, memory_map=False, float_precision=None)`

下面给出了一些有用的参数:

| 参数 | 使用 |
| --- | --- |
| `file_path_or_buffer` | 文件的网址或目录位置 |
| `sep` | 代表分隔符，默认值为','，如 csv 格式(逗号分隔值) |
| `index_col` | 此参数用于将传递列作为索引，而不是 0，1，2，3…r |
| `header` | 此参数用于将传递行[int/int list]作为标题 |
| `usecols` | 此参数是仅使用传递的列[字符串列表]来制作数据框 |
| `squeeze` | 如果为真，并且只传递了一列，则返回熊猫系列 |
| `skiprows` | 此参数用于跳过新数据框中传递行 |
| `skipfooter` | 该参数用于跳过文件底部行数 |

此方法使用逗号','作为默认分隔符，但我们也可以使用自定义分隔符或正则表达式作为分隔符。
下载 csv 文件[点击此处](https://drive.google.com/drive/folders/13I1uEBwx5dbq4jLP-qYMfmY5TsxQrVoZ?usp=sharing)

## 示例

**示例 1 :** 使用默认分隔符即逗号(,)的 `read_csv()`方法

```py
# Importing pandas library
import pandas as pd

# Using the function to load
# the data of example.csv
# into a Dataframe df
df = pd.read_csv('example1.csv')

# Print the Dataframe
df
```

**输出:**

![csv file with comma](img/39829656a793de15d2e8ff6f6c23b3e2.png)

**示例 2:** 使用 `read_csv()`方法，并使用“_”作为自定义分隔符。

```py
# Importing pandas library
import pandas as pd

# Load the data of example.csv
# with '_' as custom delimiter
# into a Dataframe df
df = pd.read_csv('example2.csv',
                   sep = '_',
                   engine = 'python')

# Print the Dataframe
df
```