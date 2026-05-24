# Python：检查一个嵌套列表是否是另一个嵌套列表的子集

> 原文：[https://www.geeksforgeeks.org/python-check-if-a-nested-list-is-a-subset-of-another-nested-list/](https://www.geeksforgeeks.org/python-check-if-a-nested-list-is-a-subset-of-another-nested-list/)

给定两个列表`list1`和`list2`，检查`list2`是否是`list1`的子集，并相应地返回真或假。

**示例：**

```py
Input : list1 = [[2, 3, 1], [4, 5], [6, 8]]
        list2 = [[4, 5], [6, 8]]
Output : True

Input : list1 = [['a', 'b'], ['e'], ['c', 'd']]
        list2 = [['g']]
Output : False
```

我们来讨论几个解决问题的方法。

## 方法#1：天真的方法
取一个变量`exist`，它跟踪每个元素，不管它是否出现在`list1`中。开始一个循环，在每次迭代`i`中，检查`list1`中是否存在第`i`个元素。如果存在，将`exist`设置为`True`或`False`。

```py
# Python3 Program to Check is a nested 
# list is a subset of another nested list

def checkSubset(list1, list2):
    l1, l2 = list1[0], list2[0]
    exist = True
    for i in list2:
        if i not in list1:
            exist = False
    return exist

# Driver Code
list1 = [[2, 3, 1], [4, 5], [6, 8]]
list2 = [[4, 5], [6, 8]]
print(checkSubset(list1, list2))
```

**Output:**

```py
True
```

## 方法2：使用Python集合
将两个给定嵌套列表的每个子列表转换为元组，因为集合不能保存列表，因为它们依赖于它们的元素是不可变的，并且列表是可变的。但是将它们转换成元组效果很好。之后，只需检查`list2`的集合是否是`list1`的子集。

```py
# Python3 Program to Check is a nested 
# list is a subset of another nested list

def checkSubset(list1, list2):
    temp1 = []
    temp2 = []
    for i in list1:
        temp1.append(tuple(i))
    for i in list2:
        temp2.append(tuple(i))

    return set(temp2) < set(temp1)

# Driver Code
list1 = [[2, 3, 1], [4, 5], [6, 8]]
list2 = [[4, 5], [6, 8]]
print(checkSubset(list1, list2))
```

**Output:**

```py
True
```

## 方法3：使用`all`和`for`循环
此方法使用`for`循环检查所有元素（使用`all`）是否属于`list1`。

```py
# Python3 Program to Check is a nested 
# list is a subset of another nested list

def checkSubset(list1, list2):
    return all(x in list1 for x in list2)

# Driver Code
list1 = [[2, 3, 1], [4, 5], [6, 8]]
list2 = [[4, 5], [6, 8]]
print(checkSubset(list1, list2))
```

**Output:**

```py
True
```

## 方法#4：使用`map()`和`__contains__`
在这种方法中，我们使用Python `map()`使用“包含检查”运算符`__contains__`，检查`list1`元素是否包含在`list2`中。

```py
# Python3 Program to Check is a nested 
# list is a subset of another nested list

def checkSubset(list1, list2):
    return all(map(list1.__contains__, list2))

# Driver Code
list1 = [[2, 3, 1], [4, 5], [6, 8]]
list2 = [[4, 5], [6, 8]]
print(checkSubset(list1, list2))
```

**Output:**

```py
True
```