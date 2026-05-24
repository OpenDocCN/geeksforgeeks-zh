# 从 PySpark 数据框中删除一列或多列

> 原文：[https://www.geeksforgeeks.org/drop-one-or-multiple-columns-from-pyspark-dataframe/](https://www.geeksforgeeks.org/drop-one-or-multiple-columns-from-pyspark-dataframe/)

在本文中，我们将讨论如何删除 Pyspark 数据框中的列。

在 pyspark 中，`drop()`功能可用于从数据框中移除值/列。

> 语法：`dataframe_name.na.drop(how=“any/all”, thresh=threshold_value, subset=[“column_name_1”, “column_name_2”])`
> *   `how` – 这需要两个值中的任何一个`any`或`all`。`any`，如果任何列包含空值，则删除一行；`all`，如果所有列都包含空值，则删除一行。默认情况下，它被设置为`any`。
> *   `thresh` – 这将取整数值，并删除非空值数量小于`thresh`的行。默认情况下，它设置为`None`。
> *   `subset` – 该参数用于选择特定的列，以针对其中的空值。默认为`None`。

**创建三列学生数据框的 Python 代码：**

```py
# importing module
import pyspark

# importing sparksession from pyspark.sql module
from pyspark.sql import SparkSession

# creating sparksession and giving an app name
spark = SparkSession.builder.appName('sparkdf').getOrCreate()

# list  of employee data with 5 row values
data =[["1", "sravan", "company 1"],
       ["3", "bobby", "company 3"],
       ["2", "ojaswi", "company 2"],
       ["1", "sravan", "company 1"],
       ["3", "bobby", "company 3"],
       ["4", "rohith", "company 2"],
       ["5", "gnanesh", "company 1"]]

# specify column names
columns = ['Employee ID','Employee NAME','Company Name']

# creating a dataframe from the lists of data
dataframe = spark.createDataFrame(data,columns)

dataframe.show()
```

**输出：**

```py
+-----------+-------------+------------+
|Employee ID|Employee NAME|Company Name|
+-----------+-------------+------------+
|          1|       sravan|   company 1|
|          3|        bobby|   company 3|
|          2|       ojaswi|   company 2|
|          1|       sravan|   company 1|
|          3|        bobby|   company 3|
|          4|       rohith|   company 2|
|          5|      gnanesh|   company 1|
+-----------+-------------+------------+
```

## 例 1：删除一列

这里我们将从数据框中删除一列。

> 语法：`dataframe.drop('列名')`

**代码：**

```py
# delete single column
dataframe = dataframe.drop('Employee ID')
dataframe.show()
```

**输出：**

```py
+-------------+------------+
|Employee NAME|Company Name|
+-------------+------------+
|       sravan|   company 1|
|        bobby|   company 3|
|       ojaswi|   company 2|
|       sravan|   company 1|
|        bobby|   company 3|
|       rohith|   company 2|
|      gnanesh|   company 1|
+-------------+------------+
```

## 例 2：删除多列

这里我们将从数据框中删除多个列。

> 语法：`dataframe.drop(*(“第 1 列”, “第 2 列”, “第 n 列”))`

**代码：**

```py
# delete two columns
dataframe = dataframe.drop(*('Employee NAME',
                             'Employee ID'))
dataframe.show()
```

**输出：**

```py
+------------+
|Company Name|
+------------+
|   company 1|
|   company 3|
|   company 2|
|   company 1|
|   company 3|
|   company 2|
|   company 1|
+------------+
```

## 例 3：删除所有列

这里，我们将从 dataframe 中删除所有列，为此，我们将把列的名称作为一个列表，并将其传递到`drop()`。

```py
list = ['Employee ID','Employee NAME','Company Name']

# delete two columns
dataframe = dataframe.drop(*list)
dataframe.show()
```

**输出：**

```py
++
||
++
||
||
||
||
||
||
++
```