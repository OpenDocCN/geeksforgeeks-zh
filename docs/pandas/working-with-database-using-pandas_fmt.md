# 使用熊猫处理数据库

> 原文:[https://www.geeksforgeeks.org/working-with-database-using-pandas/](https://www.geeksforgeeks.org/working-with-database-using-pandas/)

对保存在 SQL 中的数据执行各种操作可能会导致执行非常复杂的查询，而且不容易编写。因此，为了使这项任务变得更容易，使用熊猫来做这项工作通常是有用的，熊猫是专门为数据预处理而构建的，比 SQL 更简单和用户友好。

有时数据存储在 SQL 中，我们希望用 python 从 SQL 中获取数据，然后使用 pandas 执行操作，这种情况可能会出现。让我们看看如何使用熊猫与 SQL 数据库进行交互。

这是我们将要处理的数据库：[糖尿病_数据](https://contribute.geeksforgeeks.org/wp-content/uploads/diabetes21.csv)

**注:** 假设我们把数据存储在 `sqlite3` 中。

## 读取数据

```py
# import the libraries
import sqlite3
import pandas as pd

# create a connection
con = sqlite3.connect('Diabetes.db')

# read data from SQL to pandas dataframe.
data = pd.read_sql_query('Select * from Diabetes;', con)

# show top 5 rows
data.head()
```

**输出**

![pandas-databse](img/73fb56bd48028e5b775ff7f1a54d3dc8.png)

## 基本操作

### 行切片

```py
# read the data from sql to pandas dataframe.
data = pd.read_sql_query('Select * from Diabetes;', con)

# slicing the number of rows 
df1 = data[10:15]
df1
```

**输出**

![pandas database](img/11a9d16b644a96bb534594590aef303e.png)

### 选择特定列

选择特定的列或从数据框中选择若干列，以便进行进一步的数据处理。

```py
# read the data from sql to
# pandas dataframe.
data = pd.read_sql_query('Select * from Diabetes;', con)

# selecting specific columns.
df2 = data.loc[:, ['Glucose', 'BloodPressure']].head()
df2
```

**输出:**

![pandas database](img/0d99b6015952a9218c4d37236137906b.png)

### 汇总数据

为了从数据中获得洞察，我们必须有数据的统计摘要。要显示数据的统计摘要，如均值、中位数、众数、标准差等，我们执行以下操作。

```py
# read the data from sql 
# to pandas dataframe.
data = pd.read_sql_query('Select * from Diabetes;', con)

# summarize the data
data.describe()
```

**输出:**

![pandas database](img/a23ee68d6e7bf77f93565eacb6a7b33a.png)

### 按列排序

根据给定的列值对数据框进行排序。

```py
# read the data from sql 
# to pandas dataframe.
data = pd.read_sql_query('Select * from Diabetes;', con)

# sort data with respect 
# to particular column.
data.sort_values(by ='Age').head()
```

**输出:**

![pandas database](img/d19909799748440d4a4cc88f450f8524.png)

### 显示每列的均值

显示数据框中每一列的均值。

```py
# read the data from sql 
# to pandas dataframe.
data = pd.read_sql_query('Select * from Diabetes;', con)

# count number of rows and columns
data.mean()
```

**输出:**

![pandas database](img/d7d3e351f93c6726985f41626b84a059.png)