# Python 中特定关键字的字典数据分组列表

> 原文：[https://www.geeksforgeeks.org/group-list-of-dictionary-data-by-particular-key-in-python/](https://www.geeksforgeeks.org/group-list-of-dictionary-data-by-particular-key-in-python/)

Python 中特定关键字的字典数据分组列表可以使用 [`itertools.groupby()`](https://www.geeksforgeeks.org/itertools-groupby-in-python/) 方法完成。

## `itertools.groupby()` 简介

此方法计算 iterable 中每个元素的键。它返回分组项的关键字和可重复项。

> **语法:** `itertools.groupby(iterable, key_func)`
>
> **参数:**
>
> *   **iterable:** 可迭代可以是任何类型（列表、元组、字典）。
> *   **key_func:** 为 iterable 中存在的每个元素计算键的函数。
>
> **返回类型:** 它从 iterable 中返回连续的键和组。如果键函数未指定或为 `None`，则键默认为标识函数，并返回元素不变。

让我们看看例子：

**例子 1:** 假设我们有员工和公司的字典列表。

```py
INFO = [
    {'employee': 'XYZ_1', 'company': 'ABC_1'},
    {'employee': 'XYZ_2', 'company': 'ABC_2'},
    {'employee': 'XYZ_3', 'company': 'ABC_3'},
    {'employee': 'XYZ_4', 'company': 'ABC_3'},
    {'employee': 'XYZ_5', 'company': 'ABC_2'},
    {'employee': 'XYZ_6', 'company': 'ABC_3'},
    {'employee': 'XYZ_7', 'company': 'ABC_1'},
    {'employee': 'XYZ_8', 'company': 'ABC_2'},
    {'employee': 'XYZ_9', 'company': 'ABC_1'}
]
```

现在，我们需要按 `company` 关键字名称显示所有数据组。

**示例代码：**

```py
# import a groupby() method
# from itertools module
from itertools import groupby

# dictionary
INFO = [
    {'employee': 'XYZ_1', 'company': 'ABC_1'},
    {'employee': 'XYZ_2', 'company': 'ABC_2'},
    {'employee': 'XYZ_3', 'company': 'ABC_3'},
    {'employee': 'XYZ_4', 'company': 'ABC_3'},
    {'employee': 'XYZ_5', 'company': 'ABC_2'},
    {'employee': 'XYZ_6', 'company': 'ABC_3'},
    {'employee': 'XYZ_7', 'company': 'ABC_1'},
    {'employee': 'XYZ_8', 'company': 'ABC_2'},
    {'employee': 'XYZ_9', 'company': 'ABC_1'}
]

# define a fuction for key
def key_func(k):
    return k['company']

# sort INFO data by 'company' key.
INFO = sorted(INFO, key=key_func)

for key, value in groupby(INFO, key_func):
    print(key)
    print(list(value))
```

**输出:**

```
ABC_1
[{'employee': 'XYZ_1', 'company': 'ABC_1'}, {'employee': 'XYZ_7', 'company': 'ABC_1'}, {'employee': 'XYZ_9', 'company': 'ABC_1'}]
ABC_2
[{'employee': 'XYZ_2', 'company': 'ABC_2'}, {'employee': 'XYZ_5', 'company': 'ABC_2'}, {'employee': 'XYZ_8', 'company': 'ABC_2'}]
ABC_3
[{'employee': 'XYZ_3', 'company': 'ABC_3'}, {'employee': 'XYZ_4', 'company': 'ABC_3'}, {'employee': 'XYZ_6', 'company': 'ABC_3'}]
```

**例 2:** 假设我们有学生成绩和分数的字典列表。

```py
students = [
    {'mark': '65','grade': 'C'},
    {'mark': '86','grade': 'A'},
    {'mark': '73','grade': 'B'},
    {'mark': '49','grade': 'D'},
    {'mark': '91','grade': 'A'},
    {'mark': '79','grade': 'B'}
]
```

现在我们需要通过 `grade` 键显示所有的数据组。

**示例代码：**

```py
# import required methods
from itertools import groupby
from operator import itemgetter

# dictionary
students = [
    {'mark': '65', 'grade': 'C'},
    {'mark': '86', 'grade': 'A'},
    {'mark': '73', 'grade': 'B'},
    {'mark': '49', 'grade': 'D'},
    {'mark': '91', 'grade': 'A'},
    {'mark': '79', 'grade': 'B'}
]

# Sort students data by grade key.
students = sorted(students,
                  key = itemgetter('grade'))

# Display data grouped by grade
for key, value in groupby(students,
                          key = itemgetter('grade')):
    print(key)
    for k in value:
        print(k)
```

**输出:**

```
A
{'mark': '86', 'grade': 'A'}
{'mark': '91', 'grade': 'A'}
B
{'mark': '73', 'grade': 'B'}
{'mark': '79', 'grade': 'B'}
C
{'mark': '65', 'grade': 'C'}
D
{'mark': '49', 'grade': 'D'}
```