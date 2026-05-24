# Python–跨列表的不相交字符串

> 原文: [https://www.geeksforgeeks.org/python-disjoint-strings-across-lists/](https://www.geeksforgeeks.org/python-disjoint-strings-across-lists/)

给定两个列表，提取所有不相交的字符串对，即没有任何共同的字符。

> **输入**: `test_list1 = ["haritha", "is", "best"]`, `test_list2 = ["she", "loves", "papaya"]`
> **输出**: `[('haritha', 'loves'), ('is', 'papaya'), ('best', 'papaya')]`
> **解释**: “is”和“papaya”没有共同的字符。
>
> **输入**: `test_list1 = ["aa", "cab"]`, `test_list2 = ["a", "c"]`
> **输出**: `[]`
> **解释**: 无不相交字符串对。

## 处理方法: 利用 `set()` + `yield`【生成器】+ `reduce()` + 递归

在本文中，我们使用 `set` 的 `&` 操作执行获取不相交字符串的任务，并使用 `yield` 动态提取。使用递归检查每个后续字符串是否不相交。

### Python 3

```py
# Python3 code to demonstrate working of
# Disjoint Strings across Lists
# Using set() + yield [ generator ] + reduce() + recursion
from functools import reduce

# helper function
def dis_pairs(dpair, res=[]):

    # checking for disjoint pair
    if not dpair and not reduce(lambda a, b: set(a) & set(b), res):
        yield tuple(res)

    # recurring for subsequent pairs
    elif dpair:
        yield from [idx for k in dpair[0] for idx in dis_pairs(dpair[1:], res + [k])]

# initializing lists
test_list1 = ["haritha", "is", "best"]
test_list2 = ["she", "loves", "papaya"]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# calling function
res = list(dis_pairs([test_list1, test_list2]))

# printing result
print("All possible Disjoint pairs : " + str(res))
```

**输出:**

> 原列表 1 为: `['haritha', 'is', 'best']`
> 原列表 2 为: `['she', 'loves', 'papaya']`
> 所有可能的不相交对: `[('haritha', 'loves'), ('is', 'papaya'), ('best', 'papaya')]`