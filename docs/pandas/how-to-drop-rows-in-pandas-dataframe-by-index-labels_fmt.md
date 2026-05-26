# 如何通过索引标签删除熊猫数据框中的行？

> 原文：[https://www.geeksforgeeks.org/how-to-drop-rows-in-pandas-dataframe-by-index-labels/](https://www.geeksforgeeks.org/how-to-drop-rows-in-pandas-dataframe-by-index-labels/)

熊猫为数据分析师提供了一种使用 [`drop()`](https://www.geeksforgeeks.org/python-delete-rows-columns-from-dataframe-using-pandas-drop/) 方法来删除和过滤数据帧的方法。使用此方法，可以使用索引标签或列名删除行。

## 语法

`DataFrame.drop(labels=None, axis=0, index=None, columns=None, level=None, inplace=False, errors='raise')`

**参数：**

- `labels`：引用行或列名称的字符串或字符串列表。
- `axis`：`int` 或 `string` 值，`0` 或 `'index'` 代表行，`1` 或 `'columns'` 代表列。
- `index` 或 `columns`：单个标签或列表。`index` 或 `columns` 是 `axis` 的替代项，不能一起使用。
- `level`：用于指定数据帧有多级索引时的级别。
- `inplace`：如果为 `True`，则对原始数据框进行更改。
- `error`：如果列表中没有任何值，则忽略错误，并在 `errors='ignore'` 时丢弃其余值。

**返回类型：** 具有丢弃值的数据框

现在，让我们创建一个示例数据框。

## 示例代码

```py
# import pandas library
import pandas as pd

# dictionary with list object in values
details = {
    'Name' : ['Ankit', 'Aishwarya', 'Shaurya','Shivangi'],
    'Age' : [23, 21, 22,21],
    'University' : ['BHU', 'JNU', 'DU', 'BHU'],
}

# creating a Dataframe object
df = pd.DataFrame(details,columns = ['Name','Age','University'],
                  index = ['a', 'b', 'c', 'd'])

df
```

**输出：**

![pandas-drop-row-1](img/727b13949f4f41d68f26eb3eace85006.png)

## 示例#1：按行索引标签删除数据框中的单个行

```py
# import pandas library
import pandas as pd

# dictionary with list object in values
details = {
    'Name' : ['Ankit', 'Aishwarya', 'Shaurya', 'Shivangi'],
    'Age' : [23, 21, 22, 21],
    'University' : ['BHU', 'JNU', 'DU', 'BHU'],
}

# creating a Dataframe object
df = pd.DataFrame(details, columns = ['Name', 'Age', 'University'],
                  index = ['a', 'b', 'c', 'd'])

# return a new dataframe by dropping a
# row 'c' from dataframe
update_df = df.drop('c')

update_df
```

**输出：**

![drop-rows-2](img/ff6b9cf2e34a415d45048769ab97d94b.png)

## 示例#2：通过索引标签删除数据框中的多行

```py
# import pandas library
import pandas as pd

# dictionary with list object in values
details = {
    'Name' : ['Ankit', 'Aishwarya', 'Shaurya', 'Shivangi'],
    'Age' : [23, 21, 22, 21],
    'University' : ['BHU', 'JNU', 'DU', 'BHU'],
}

# creating a Dataframe object
df = pd.DataFrame(details, columns = ['Name', 'Age', 'University'],
                  index = ['a', 'b', 'c', 'd'])

# return a new dataframe by dropping a row
# 'b' & 'c' from dataframe
update_df = df.drop(['b', 'c'])

update_df
```

**输出：**

![pandas-drop-row-3](img/084b50643d3ebb97bdb336d4c3826687.png)

## 示例#3：按数据框中的索引位置删除多行

```py
# import pandas library
import pandas as pd

# dictionary with list object in values
details = {
    'Name' : ['Ankit', 'Aishwarya', 'Shaurya', 'Shivangi'],
    'Age' : [23, 21, 22, 21],
    'University' : ['BHU', 'JNU', 'DU', 'BHU'],
}

# creating a Dataframe object
df = pd.DataFrame(details, columns = ['Name', 'Age', 'University'],
                  index = ['a', 'b', 'c', 'd'])

# return a new dataframe by dropping a row
# 'b' & 'c' from dataframe using their
# respective index position
update_df = df.drop([df.index[1], df.index[2]])

update_df
```

**输出：**

![pandas-drop-row](img/79aa74ca55bffa681c29029b8cf11406.png)

## 示例#4：就地删除数据框中的行

```py
# import pandas library
import pandas as pd

# dictionary with list object in values
details = {
    'Name' : ['Ankit', 'Aishwarya', 'Shaurya', 'Shivangi'],
    'Age' : [23, 21, 22, 21],
    'University' : ['BHU', 'JNU', 'DU', 'BHU'],
}

# creating a Dataframe object
df = pd.DataFrame(details, columns = ['Name', 'Age', 'University'],
                  index = ['a', 'b', 'c', 'd'])

# dropping a row 'c' & 'd' from actual dataframe
df.drop(['c', 'd'], inplace = True )

df
```

**输出：**

![pandas-drop-row-6](img/309ff24512e0f62341573e4cdc86f801.png)