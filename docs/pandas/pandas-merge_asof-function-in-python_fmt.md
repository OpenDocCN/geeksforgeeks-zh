# pandas.merge_asof()函数在 Python 中

> 原文: [https://www.geeksforgeeks.org/pandas-merge_asof-function-in-python/](https://www.geeksforgeeks.org/pandas-merge_asof-function-in-python/)

此方法用于执行 asof 合并。这类似于左连接，只是我们匹配最近的键而不是相等的键。两个数据帧都必须按关键字排序。

> **语法:** `pandas.merge_asof(left, right, on=None, left_on=None, right_on=None, left_index=False, right_index=False, by=None, left_by=None, right_by=None, suffixes=('_x', '_y'), tolerance=None, allow_exact_matches=True, direction='backward')`
>
> **参数:**
>
> *   `left`, `right`: 数据框
> *   `on`: 标签，要加入的字段名。必须在两个数据帧中找到。
> *   `left_on`: 标签，要在左侧数据框中加入的字段名。
> *   `right_on`: 标签，要加入右侧数据框的字段名。
> *   `left_index`: boolean，使用左侧 DataFrame 的索引作为连接键。
> *   `right_index`: boolean，使用右侧 DataFrame 的索引作为连接键。

下面是上述方法的实现，并附有一些例子:

## 例 1

```py
# importing package
import pandas

# creating data
left = pandas.DataFrame({'a': [1, 5, 10],
                         'left_val': ['a', 'b', 'c']})

right = pandas.DataFrame({'a': [1, 2, 3, 6, 7],
                          'right_val': [1, 2, 3, 6, 7]})

# view data
print(left)
print(right)

# applying merge_asof on data
print(pandas.merge_asof(left, right, on='a'))
print(pandas.merge_asof(left, right, on='a',
                        allow_exact_matches=False))
```

**输出:**

![](img/348ed991b848c4dd0eee85f3395b5c26.png)

## 例 2

```py
# importing package
import pandas

# creating data
left = pandas.DataFrame({'a': [1, 5, 10],
                         'left_val': ['a', 'b', 'c']})

right = pandas.DataFrame({'a': [1, 2, 3, 6, 7],
                          'right_val': [1, 2, 3, 6, 7]})

# view data
print(left)
print(right)

# applying merge_asof on data
print(pandas.merge_asof(left, right, on='a',
                        direction='forward'))
print(pandas.merge_asof(left, right, on='a',
                        direction='nearest'))
```

**输出:**

![](img/21b72287dc13320e15eb20ca43984fb7.png)

## 例 3

```py
# importing package
import pandas

# creating data
left = pandas.DataFrame({'left_val': ['a', 'b', 'c']},
                        index=[1, 5, 10])

right = pandas.DataFrame({'right_val': [1, 2, 3, 6, 7]},
                         index=[1, 2, 3, 6, 7])

# view data
print(left)
print(right)

# applying merge_asof on data
print(pandas.merge_asof(left, right, left_index=True,
                        right_index=True))
```

**输出:**

![](img/107158d29c93fdcca6c114eaeec2e1f2.png)