# Python：统计列表中包含给定元素的子列表

> 原文：[https://www.geeksforgeeks.org/python-count-the-sublists-containing-given-element-in-a-list/](https://www.geeksforgeeks.org/python-count-the-sublists-containing-given-element-in-a-list/)

给定一个列表的列表，编写一个 Python 程序来计算包含给定元素 `x` 的子列表的数量。

**示例：**

```py
Input : lst = [[1, 3, 5], [1, 3, 5, 7], [1, 3, 5, 7, 9]] 
        x = 1 
Output : 3

Input : lst = [['a'], ['a', 'c', 'b'], ['d']] 
        x = 'a'
Output : 2
```

## 方法 1：朴素方法

统计包含 `x` 的列表数量。初始化 `count` 为 0，然后开始一个 `for` 循环，检查每个列表中是否存在 `x`。如果是，增加 `count`。

```py
# Python3 Program to count number of
# list containing a certain element 
# in a list of lists

def countList(lst, x):
    count = 0
    for i in range(len(lst)):
        if x in lst[i]:
            count+= 1

    return count

# Driver Code
lst = [['a'], ['a', 'c', 'b'], ['d']] 
x = 'a'
print(countList(lst, x))
```

**输出：**

```py
2
```

## 方法 2：列表推导式（朴素方法的替代）

简单的一行列表推导式也可以通过将上述朴素方法转换为循环的一行来完成这项工作。

```py
# Python3 Program to count number of
# list containing a certain element 
# in a list of lists

def countList(lst, x):
    return sum(x in item for item in lst)

# Driver Code
lst = [['a'], ['a', 'c', 'b'], ['d']] 
x = 'a'
print(countList(lst, x))
```

**输出：**

```py
2
```

## 方法 3：使用 `chain.from_iterable()` 和 `Counter`

我们可以使用 `Counter` 来计算列表中出现了多少个 `x`。因为我们不想为每个内部列表多次计算 `x`，所以我们将把每个内部列表转换成集合。之后，使用 `chain.from_iterable()` 将这些元素集合连接成一个序列。

```py
# Python3 Program to count number of
# list containing a certain element 
# in a list of lists
from itertools import chain
from collections import Counter

def countList(lst, x):
    return Counter(chain.from_iterable(set(i) for i in lst))[x]

# Driver Code
lst = [['a'], ['a', 'c', 'b'], ['d']] 
x = 'a'
print(countList(lst, x))
```

**输出：**

```py
2
```