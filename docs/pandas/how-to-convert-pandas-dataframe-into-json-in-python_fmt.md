# 如何用 Python 将熊猫 DataFrame 转换成 JSON？

> 原文：[https://www.geeksforgeeks.org/how-to-convert-pandas-dataframe-into-json-in-python/](https://www.geeksforgeeks.org/how-to-convert-pandas-dataframe-into-json-in-python/)

数据分析是当今世界极其重要的工具。数据分析的一个关键方面是数据的有组织的表示。在计算机科学中有许多数据结构来实现这一任务。在本文中，我们将讨论两种这样的数据结构，即`熊猫数据框`和`JSON`。此外，我们还将看到如何将数据帧转换为`JSON`格式。

`熊猫数据帧`是数据的表格表示，其中列表示单个数据条目中的不同数据点，每行是唯一的数据条目。而`JSON`是用`JavaScript`对象符号编写的文本。

**注：**更多信息请参考 [Python | 熊猫数据框](http://geeksforgeeks.org/python-pandas-dataframe/)

## 将熊猫数据帧转换为 JSON

要将`熊猫数据帧`转换为`JSON`格式，我们使用`Python`中`熊猫`库的函数`DataFrame.to_json()`。`to_json`函数中有多种定制，可以实现所需的`json`格式。让我们看看函数接受的参数，然后探索定制。

**参数：**

| 参数 | 价值 | 使用 |
| --- | --- | --- |
| `path_or_buf` | 字符串或文件名，可选 | 文件路径或对象。如果未指定，结果将作为字符串返回。 |
| `orient` | `'split'`，`'records'`，`'index'`，`'columns'`，`'values'`，`'table'`，默认值=`'index'` | 预期`JSON`字符串格式的指示。 |
| `date_format` | `None`，`'epoch'`，`'iso'`，默认值=`'epoch'` | 日期转换的类型。`'epoch'` = epoch 毫秒，`'iso'` = ISO8601。默认值取决于`orient`。对于`orient='table'`，默认值为`'iso'`。对于所有其他方向，默认为`'epoch'`。 |
| `double_precision` | 整数值，默认值=`10` | 对浮点值进行编码时使用的小数位数。 |
| `force_ascii` | 布尔值，默认值=`True` | 强制编码字符串为 ASCII。 |
| `date_unit` | `'s'`，`'ms'`，`'us'`，`'ns'`，默认值=`'ms'` | 要编码到的时间单位，控制时间戳和 ISO8601 精度。这些值分别代表秒、毫秒、微秒和纳秒。 |
| `default_handler` | 可调用函数 | 如果对象不能转换为适合`JSON`的格式，则调用处理程序。应该接收单个参数，该参数是要转换并返回可序列化对象的对象。 |
| `lines` | 布尔值，默认值=`False` | 如果`"orient"`是`"records"`，写出以行分隔的`json`格式。如果`"orient"`不正确，将抛出`ValueError`，因为其他值不像列表。 |
| `compression` | `'infer'`，`'gzip'`，`'bz2'`，`'zip'`，`'xz'`，`None`，默认=`'infer'` | 一个字符串，表示要在输出文件中使用的压缩，仅当第一个参数是文件名时使用。默认情况下，压缩是从文件名推断出来的。 |
| `index` | 布尔值，默认值=`True` | 是否在`JSON`字符串中包含索引值。仅当`orient`为`'split'`或`'table'`时，才支持不包括索引(`index=False`)。 |
| `indent` | 整数值 | 用于缩进每条记录的空白长度。可选参数无需提及。 |

我们现在看几个例子来理解函数`DataFrame.to_json`的用法。

**例 1：** 基本用法

```py
import numpy as np
import pandas as pd

data = np.array([['1', '2'], ['3', '4']])

dataFrame = pd.DataFrame(data, columns = ['col1', 'col2'])
json = dataFrame.to_json()
print(json)
```

**输出：**

```py
{"col1":{"0":"1", "1":"3"}, "col2":{"0":"2", "1":"4"}}
```

**例 2：** 探索`DataFrame.to_json`函数的`'orient'`属性

```py
import numpy as np
import pandas as pd

data = np.array([['1', '2'], ['3', '4']])

dataFrame = pd.DataFrame(data, columns = ['col1', 'col2'])
json = dataFrame.to_json()
print(json)

json_split = dataFrame.to_json(orient ='split')
print("json_split = ", json_split, "\n")

json_records = dataFrame.to_json(orient ='records')
print("json_records = ", json_records, "\n")

json_index = dataFrame.to_json(orient ='index')
print("json_index = ", json_index, "\n")

json_columns = dataFrame.to_json(orient ='columns')
print("json_columns = ", json_columns, "\n")

json_values = dataFrame.to_json(orient ='values')
print("json_values = ", json_values, "\n")

json_table = dataFrame.to_json(orient ='table')
print("json_table = ", json_table, "\n")
```

**输出：**

> json_split = {"columns":["col1", "col2"], "index":[0, 1], "data":[["1", "2"], ["3", "4"]]}
>
> json_records = [{"col1":"1", "col2":"2"}, {"col1":"3", "col2":"4"}]
>
> json_index = {"0":{"col1":"1", "col2":"2"}, "1":{"col1":"3", "col2":"4"}}
>
> json_columns = {"col1":{"0":"1", "1":"3"}, "col2":{"0":"2", "1":"4"}}
>
> json_values = [["1", "2"], ["3", "4"]]
>
> json_table = {"schema":{"fields":[{"name":"index", "type":"integer"}, {"name":"col1", "type":"string"}, {"name":"col2", "type":"string"}], "primaryKey":["index"], "pandas_version":"0.20.0"}, "data":[{"index":0, "col1":"1", "col2":"2"}, {"index":1, "col1":"3", "col2":"4"}]}