# Python – 获取列表中某个元素所有出现的索引

> 原文: [https://www.geeksforgeeks.org/python-get-the-indices-of-all-occurrences-of-an-element-in-a-list/](https://www.geeksforgeeks.org/python-get-the-indices-of-all-occurrences-of-an-element-in-a-list/)

给定一个列表，任务是编写一个 Python 程序来获取列表中所有元素的索引。

## 方法 1: 使用 for 循环

这是一个简单的方法来获取列表中所有出现的元素的索引。这里我们使用一个 for 循环来遍历原始列表中的每个元素。

> **语法:** `range(长度)`
> **其中**
> *   `长度` 是列表的大小

**示例:**

### Python 3

```py
# initialize a list
my_list = [1, 2, 3, 1, 5, 4]

# find length of the list
list_size = len(my_list)

# declare for loop
for itr in range(list_size):
    # check the condition
    if(my_list[itr] == 1):
        # print the indices
        print(itr)
```

**输出:**

```py
0
3
```

## 方法二: 使用 `enumerate()` 函数

我们可以使用 `enumerate` 函数来代替 for 循环。此函数向 iterable 添加一个计数器，并返回枚举对象。

> **语法:** `[ind for ind, ele in enumerate(list_name) if ele == 元素名称]`
> **其中**
> *   `元素名称` 是元素的名称
> *   `list_name` 是列表的名称
> *   `条件` 是需要为真的条件

为此，我们将创建列表，然后我们将创建枚举函数来获取列表中所有元素的索引。

**示例:**

### Python 3

```py
# initialize a list
my_list = [1, 2, 3, 1, 5, 4]
indices = [ind for ind, ele in enumerate(my_list) if ele == 1]

# print the indices
print(indices)
```

**输出:**

```py
[0, 3]
```

## 方法 3: 使用 `itertools` 模块

`Itertools` 是内存高效的工具，它们本身或组合起来都很有用，因此为此，我们将使用这个模块中的 `count()` 方法，该方法将从起始值返回一个等间距值的迭代器。

> **语法:** `[ind for ind, ele in zip(count(), list_name) if ele == 元素名称]`
> *   `元素名称` 是元素的名称
> *   `list_name` 是列表的名称
> *   `条件` 是需要为真的条件

为此，我们将创建一个列表，然后使用带有 `zip()` 的理解，我们将获得列表中所有元素的索引。

**示例:**

### Python 3

```py
# import count method from itertools
from itertools import count

# initialize a list
my_list = [1, 2, 3, 1, 5, 4]
indices = [ind for ind,
           ele in zip(count(),
                      my_list) if ele == 1]

# print the indices
print(indices)
```

**输出:**

```py
[0, 3]
```

## 方法四: 使用 `NumPy` 库

`NumPy` 是通用的数组处理包，它提供了在 Python 中使用数组的便捷方式。

> **语法:** `numpy.where(list_name, value)[index]`
> **其中**
> *   `list_name` 是列表的名称
> *   `值` 是要搜索的值
> *   `索引` 是数组的起始索引(通常为 `0`)

为此，我们将使用 `numpy.array()` 创建一个数组，然后在条件满足时使用 `numpy.where()` 方法获取输入数组中元素的所有索引。

**示例:**

### Python 3

```py
# import numpy module
import numpy

# initialize a array
my_list = numpy.array([1, 2, 3, 1, 5, 4])
indices = numpy.where(my_list == 1)[0]

# display result
print(indices)
```

**输出:**

```py
[0, 3]
```