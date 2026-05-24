# PySpark 数据框 – 将字符串映射到数字

> 原文: [https://www.geeksforgeeks.org/pyspark-dataframe-map-strings-to-numeric/](https://www.geeksforgeeks.org/pyspark-dataframe-map-strings-to-numeric/)

在本文中，我们将了解如何将字符串映射转换为数字。

## 正在创建用于演示的数据框与 Python 3

这里我们为学院名创建一行数据，然后传递 `createDataFrame()` 方法，最后显示 `dataframe`。

```py
# importing module
import pyspark

# importing sparksession from pyspark.sql module and Row module
from pyspark.sql import SparkSession,Row

# creating sparksession and giving an app name
spark = SparkSession.builder.appName('sparkdf').getOrCreate()

# list  of college data
dataframe = spark.createDataFrame([Row("vignan"),
                                   Row("rvrjc"),
                                   Row("klu"),
                                   Row("rvrjc"),
                                   Row("klu"),
                                   Row("vignan"),
                                   Row("iit")],
                                  ["college"])

# display dataframe
dataframe.show()
```