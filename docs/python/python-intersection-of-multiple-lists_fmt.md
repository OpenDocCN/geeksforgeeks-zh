# Python | 多个列表的交集

> 原文: [https://www.geeksforgeeks.org/python-intersection-of-multiple-lists/](https://www.geeksforgeeks.org/python-intersection-of-multiple-lists/)

给定两个列表，编写一个 Python 程序来查找给定的两个列表之间的交集。

## 示例

```py
Input : lst1 = [['a', 'c'], ['d', 'e']]
        lst2 = [['a', 'c'], ['e', 'f'], ['d', 'e']]
Output : [['a', 'c'], ['d', 'e']]

Input : lst1 = [[1, 5, 7], [2, 3], [6, 9], [4, 8]]
        lst2 = [[9, 3], [2, 3], [6, 9]]
Output : [[2, 3], [6, 9]]
```

## 方法 1：朴素方法（列表推导式）

寻找列表交集的强力或朴素方法是使用列表推导式或简单的循环。

```py
# Python3 program to find
# Intersection of list of lists

def intersection(lst1, lst2):
    return [item for item in lst1 if item in lst2]

# Driver code
lst1 = [['a', 'c'], ['d', 'e']]
lst2 = [['a', 'c'], ['e', 'f'], ['d', 'e']]
print(intersection(lst1, lst2))
```

**输出：**

```py
[['a', 'c'], ['d', 'e']]
```

## 方法 2：使用集合的 `intersection()` 方法

与朴素方法相比，这是一种更高效的方法。我们首先使用 `map()` 将这两个列表转换为元组列表，因为 Python 集合与元组兼容，而不是列表。然后我们简单地找到这两个列表的集合 `intersection()`。

```py
# Python3 program to find
# Intersection of list of list

def intersection(lst1, lst2):
    tup1 = map(tuple, lst1)
    tup2 = map(tuple, lst2)
    return list(map(list, set(tup1).intersection(tup2)))

# Driver code
lst1 = [['a', 'c'], ['d', 'e']]
lst2 = [['a', 'c'], ['e', 'f'], ['d', 'e']]
print(intersection(lst1, lst2))
```

**输出：**

```py
[['d', 'e'], ['a', 'c']]
```