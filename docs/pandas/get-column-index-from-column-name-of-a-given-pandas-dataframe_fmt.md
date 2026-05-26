# 从给定熊猫数据框的列名中获取列索引

> 原文: [https://www.geeksforgeeks.org/get-column-index-from-column-name-of-a-given-pandas-dataframe/](https://www.geeksforgeeks.org/get-column-index-from-column-name-of-a-given-pandas-dataframe/)

在本文中，我们将看到如何从数据帧的列名中获取列索引。我们将使用`dataframe.columns`属性和`index.get_loc()`方法的`熊猫`模块结合在一起。

> **语法:** `dataframe.columns`
>
> **返回:** 列名索引
>
> **语法:** `Index.get_loc(key, method=None, tolerance=None)`
>
> **返回:** loc: 如果索引唯一，则为 int，如果索引单调，则为 slice，否则为 mask

**代码:** 让我们创建一个数据帧:

## Python 3

```py
# import pandas library
import pandas as pd

# dictionary
record = {'Math': [10, 20, 30,
                   40, 70],
          'Science': [40, 50, 60,
                      90, 50],
          'English': [70, 80, 66,
                      75, 88]}

# create a dataframe
df = pd.DataFrame(record)

# show the dataframe
print(df)
```

**输出:**

![Dataframe](img/c840ec91c4e71c6d9ac63e923394222a.png)

数据帧

**例 1:** 获取“科学”一栏的索引号。

## Python 3

```py
# import pandas library
import pandas as pd

# dictionary
record = {'Math': [10, 20, 30, 40, 70],
          'Science': [40, 50, 60, 90, 50],
          'English': [70, 80, 66, 75, 88]}

# give column name
col_name = "Science"

# find the index no
index_no = df.columns.get_loc(col_name)

print("Index of {} column in given dataframe is : {}".format(col_name, index_no))
```

**输出:**

![index number of Science column](img/e11fd4aaaaec78b5ba44814dd8c2bafc.png)

科学专栏索引号

**例 2:** 获取“英语”列的索引号。

## Python 3

```py
# import pandas library
import pandas as pd

# dictionary
record = {'Math': [10, 20, 30,
                   40, 70],
          'Science': [40, 50, 60,
                      90, 50],
          'English': [70, 80, 66,
                      75, 88]}

# create a dataframe
df = pd.DataFrame(record)

# give column name
col_name = "English"

# find the index no
index_no = df.columns.get_loc(col_name)

print("Index of {} column in given dataframe is : {}".format(col_name, index_no))
```

**输出:**

![index number of English column](img/39b6ab3d058bccb579f442aa4ad459b5.png)

英文栏目索引号