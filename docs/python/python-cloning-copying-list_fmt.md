# Python | 克隆或复制列表

> 原文: [https://www.geeksforgeeks.org/python-cloning-copying-list/](https://www.geeksforgeeks.org/python-cloning-copying-list/)

在本文中，我们将介绍在 Python 中复制或克隆列表的各种方法。这些不同的复制方式需要不同的执行时间，所以我们可以根据时间进行比较。

## 1. `Using slicing technique`
这是克隆列表最简单、最快的方法。当我们想要修改列表同时保留原始列表的副本时，可以考虑此方法。在此方法中，我们复制列表本身及其引用。此过程也称为克隆。该技术大约需要 0.039 秒，是最快的技术。

```py
# Python program to copy or clone a list
# Using the Slice Operator
def Cloning(li1):
    li_copy = li1[:]
    return li_copy

# Driver Code
li1 = [4, 8, 2, 10, 15, 18]
li2 = Cloning(li1)
print("Original List:", li1)
print("After Cloning:", li2)
```

输出:
```
Original List: [4, 8, 2, 10, 15, 18]
After Cloning: [4, 8, 2, 10, 15, 18]
```

## 2. `使用 extend()方法`
可以使用 `extend()` 函数将列表复制到新列表中。这会将可迭代对象的每个元素（例如，一个列表）附加到新列表的末尾。这大约需要 0.053 秒来完成。
示例:

```py
# Python code to clone or copy a list
# Using the in-built function extend()
def Cloning(li1):
    li_copy = []
    li_copy.extend(li1)
    return li_copy

# Driver Code
li1 = [4, 8, 2, 10, 15, 18]
li2 = Cloning(li1)
print("Original List:", li1)
print("After Cloning:", li2)
```

输出:
```
Original List: [4, 8, 2, 10, 15, 18]
After Cloning: [4, 8, 2, 10, 15, 18]
```

## 3. `Using the list() method`
这是使用内置函数 `list()` 克隆列表的最简单方法。这大约需要 0.075 秒来完成。
示例:

```py
# Python code to clone or copy a list
# Using the in-built function list()
def Cloning(li1):
    li_copy = list(li1)
    return li_copy

# Driver Code
li1 = [4, 8, 2, 10, 15, 18]
li2 = Cloning(li1)
print("Original List:", li1)
print("After Cloning:", li2)
```

输出:
```
Original List: [4, 8, 2, 10, 15, 18]
After Cloning: [4, 8, 2, 10, 15, 18]
```

## 4. `使用浅拷贝的方法`
使用 `copy.copy` 的这种拷贝方法在文章[浅拷贝](https://www.geeksforgeeks.org/copy-python-deep-copy-shallow-copy/)中有很好的解释。这大约需要 0.186 秒来完成。

## 5. `Using list comprehension`
列表推导式的方法可用于将所有元素从一个列表逐个复制到另一个列表。这大约需要 0.217 秒来完成。

```py
# Python code to clone or copy a list
# Using list comprehension
def Cloning(li1):
    li_copy = [i for i in li1]
    return li_copy

# Driver Code
li1 = [4, 8, 2, 10, 15, 18]
li2 = Cloning(li1)
print("Original List:", li1)
print("After Cloning:", li2)
```

输出:
```
Original List: [4, 8, 2, 10, 15, 18]
After Cloning: [4, 8, 2, 10, 15, 18]
```

## 6. `Using the append() method`
这可用于向列表追加和添加元素，或将它们复制到新列表。它用于将元素添加到列表的最后位置。这大约需要 0.325 秒来完成，是最慢的克隆方法。

```py
# Python code to clone or copy a list
# Using append()
def Cloning(li1):
    li_copy = []
    for item in li1:
        li_copy.append(item)
    return li_copy

# Driver Code
li1 = [4, 8, 2, 10, 15, 18]
li2 = Cloning(li1)
print("Original List:", li1)
print("After Cloning:", li2)
```

输出:
```
Original List: [4, 8, 2, 10, 15, 18]
After Cloning: [4, 8, 2, 10, 15, 18]
```

## 7. `Using the copy() method`
内置方法 `copy` 用于将所有元素从一个列表复制到另一个列表。这大约需要 1.488 秒来完成。
示例:

```py
# Python code to clone or copy a list
# Using built-in method copy()
def Cloning(li1):
    li_copy = []
    li_copy = li1.copy()
    return li_copy

# Driver Code
li1 = [4, 8, 2, 10, 15, 18]
li2 = Cloning(li1)
print("Original List:", li1)
print("After Cloning:", li2)
```

输出:
```
Original List: [4, 8, 2, 10, 15, 18]
After Cloning: [4, 8, 2, 10, 15, 18]
```

## 8. `使用深度复制`
的方法这种复制方法在[深度复制](https://www.geeksforgeeks.org/copy-python-deep-copy-shallow-copy/)一文中有很好的解释。这大约需要 10.59 秒来完成，是最慢的克隆方法。

参考[堆栈溢出](https://stackoverflow.com/questions/2612802/how-to-clone-or-copy-a-list)。