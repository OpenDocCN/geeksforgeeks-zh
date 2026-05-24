# Python–连接最大元组

> 原文: [https://www.geeksforgeeks.org/python-concatenate-maximum-tuples/](https://www.geeksforgeeks.org/python-concatenate-maximum-tuples/)

给定一个包含字符串及其大小的元组列表，任务是编写一个 python 程序来连接所有具有最大大小的字符串。

**示例:**

> **输入:** `test_list = [("Gfg is best", 8), ("Gfg is good", 7), ("for", 2), ("for all geeks", 8)]`
>
> **输出:** `"Gfg is best for all geeks"`
>
> **解释:** 8 是最大元组元素，键的串联产生结果。
>
> **输入:** `test_list = [("Gfg is best", 7), ("Gfg is good", 8), ("for", 2), ("for all geeks", 8)]`
>
> **输出:** `"gfg is good for all geeks"`
>
> **解释:** 8 是最大元组元素，键的串联产生结果。

**方法一: 使用 `max()` + `itemgetter()` + 列表理解 + `join()`**

在本文中，我们使用 `max()`，`itemgetter` 处理要查询的索引来执行获取最大量值的任务。使用列表理解匹配后，字符串通过 `join()` 连接。

### Python 3

```py
# Python3 code to demonstrate working of
# Concatenate Maximum Tuples
# Using max() + itemgetter() + list comprehension + join()
from operator import itemgetter

# initializing list
test_list = [("Gfg is best", 8), ("gfg is good", 7),
             ("for", 2), ("for all geeks", 8)]

# printing original list
print("The original list is : " + str(test_list))

# getting maximum
max_ele = max(test_list, key=itemgetter(1))[1]

# joining maximum
res = ' '.join([key for key, ele in test_list if ele == max_ele])

# printing result
print("The maximum concatenated strings : " + str(res))
```

**输出:**

> 原列表为: [('Gfg is best', 8), ('gfg is good', 7), ('for', 2), ('for all geeks', 8)]
>
> 最大串联字符串: Gfg is best for all geeks

**方法 2: 使用 `filter()` + `max()` + `itemgetter()`**

在本文中，我们使用 `filter()` 而不是列表理解来执行过滤任务。其余所有功能与所有方法相似。

### Python 3

```py
# Python3 code to demonstrate working of
# Concatenate Maximum Tuples
# Using filter() + max() + itemgetter()
from operator import itemgetter

# initializing list
test_list = [("Gfg is best", 8), ("gfg is good", 7),
             ("for", 2), ("for all geeks", 8)]

# printing original list
print("The original list is : " + str(test_list))

# getting maximum
max_ele = max(test_list, key=itemgetter(1))[1]

# joining maximum
# filter checks for maximum values and concats
res = " ".join([ele[0]
                for ele in filter(lambda ele: ele[1] == max_ele, test_list)])

# printing result
print("The maximum concatenated strings : " + str(res))
```

**输出:**

> 原列表为: [('Gfg is best', 8), ('gfg is good', 7), ('for', 2), ('for all geeks', 8)]
>
> 最大串联字符串: Gfg is best for all geeks