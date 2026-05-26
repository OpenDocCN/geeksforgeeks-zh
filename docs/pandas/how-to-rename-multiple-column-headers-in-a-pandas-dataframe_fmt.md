# 如何重命名熊猫数据框中的多个列标题？

> 原文：[https://www.geeksforgeeks.org/how-to-rename-multiple-column-headers-in-a-pandas-dataframe/](https://www.geeksforgeeks.org/how-to-rename-multiple-column-headers-in-a-pandas-dataframe/)

在本文中，我们将使用 [`rename()`](https://www.geeksforgeeks.org/python-pandas-dataframe-rename/) 方法重命名多个列标题。该方法可用于重命名单个列以及一次重命名多个列。我们需要传递一个包含新值的字典作为 `columns` 参数，并设置 `inplace=True`。我们传递 `inplace=True` 是因为我们只是修改当前的工作数据框；如果我们传递 `inplace=False`，那么它会返回一个新的数据框。

**方法：**

*   导入 `pandas`。
*   创建一个具有多列的数据框。
*   创建一个字典，并将键设置为旧列名，值设置为列标题的新名称。
*   将字典分配给 `columns` 参数。
*   调用 `rename` 方法并传递包含该字典和 `inplace=True` 的 `columns` 参数。

**下面是实现：**

**示例 1：**

```py
# import pandas
import pandas as pd

# create data frame
df = pd.DataFrame({'First Name': ["Mukul", "Rohan", "Mayank",
                                  "Vedansh", "Krishna"],

'Location': ["Saharanpur", "Rampur", "Agra", 
                                "Saharanpur", "Noida"],

'Pay': [56000.0, 55000.0, 61000.0, 45000.0, 62000.0]})

# print original data frame
display(df)

# create a dictionary
# key = old name
# value = new name
dict = {'First Name': 'Name',
        'Location': 'City',
        'Pay': 'Salary'}

# call rename () method
df.rename(columns=dict,
          inplace=True)

# print Data frame after rename columns
display(df)
```

**输出：**

![](img/2f0776961193317b3f6fa61f705dadfd.png)

**示例 2：**

在本例中，我们将使用相同的方法多次重命名列。

```py
# import pandas
import pandas as pd

# create data frame
df = pd.DataFrame({'First Name': ["Mukul", "Rohan", "Mayank",
                                  "Vedansh", "Krishna"],

'Location': ["Saharanpur", "Rampur", 
                                "Agra", "Saharanpur", "Noida"],

'Pay': [56000.0, 55000.0, 61000.0, 45000.0, 62000.0]})

print("Orignal DataFrame")

# print original data frame
display(df)

# create a dictionary
# key = old name
# value = new name
dict = {'First Name': 'Name',
        'Location': 'City',
        'Pay': 'Salary'}

print("\nAfter rename")
# call rename () method
df.rename(columns=dict,
          inplace=True)

# print Data frame after rename columns
display(df)

# create a dictionary
# key = old name
# value = new name
dict = {'Name': 'Full Name',
        'City': 'Address',
        'Salary': 'Amount'}

# call rename () method
df.rename(columns=dict,
          inplace=True)

display(df)
```

**输出：**

![](img/9ea3386540c0eec9c4e73441a0375a2e.png)