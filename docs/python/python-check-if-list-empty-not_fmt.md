# Python–检查列表是否为空

> 原文: [https://www.geeksforgeeks.org/python-check-if-list-empty-not/](https://www.geeksforgeeks.org/python-check-if-list-empty-not/)

在本文中，我们将学习如何检查给定的列表是否为空。在 Python 中有各种方法可以检查列表，但是所有这些方法都不合适，或者用 Python 的术语“Python 化”来实现。

## 普通 Python 方法

1.  让我们看看如何以一种不那么 Pythonic 的方式检查列表是否为空。我们应该避免这种**显式检查序列或列表**的方式。

```py
# Python code to check for empty list
# Explicit way
def Enquiry(lis1):
    if len(lis1) == 0:
        return 0
    else:
        return 1

# Driver Code
lis1 = []
if Enquiry(lis1):
    print ("The list is not empty")
else:
    print("Empty List")
```

**输出:**

```py
Empty List
```

2.  现在让我们看看一种更 Pythonic 的检查空列表的方法。这种检查方法是一种**隐式检查方式，比前一种更可取**。

```py
# Python code to check for empty list
# IMPLICIT way or Pythonic way
def Enquiry(lis1):
    if not lis1:
        return 1
    else:
        return 0

# Driver Code
lis1 = []
if Enquiry(lis1):
    print ("The list is Empty")
else:
    print ("The list is not empty")
```

**输出:**

```py
The list is Empty
```

## Numpy 方法

1.  我们之前在普通 **Python 中使用的方法不适用于 Numpythonic 方式**。对列表或其他标准容器有效的其他方法**对 numpy 数组会失败**。这种方法对 numpy 数组失败，因为 numpy 试图将数组转换为布尔值数组，如果它试图一次性评估所有这些布尔值以获取某种聚合真值，它就会失败，因此我们得到 `ValueError`。

```py
# Numpythonic way with the previous method
# Returns ValueError
import numpy
def Enquiry(lis1):
    return(numpy.array(lis1))

# Driver Code
lis1 = [0, 1]
if Enquiry(lis1):
    print("Not Empty")
else:
    print("Empty")
```

**输出:**

```py
None
```

错误:

```py
Traceback (most recent call last):
  File "/home/2d237324bb5211d7216c521441a750e9.py", line 7, in 
    if Enquiry(lis1):
ValueError: The truth value of an array with more than 
one element is ambiguous. Use a.any() or a.all()
```

2.  在下一个例子中，我们将看到即使列表不是空的，输出也会显示为空。如果列表包含一个 `0`，那么 `if` 语句将导致错误的结果。

```py
# Numpythonic way with the previous method
# Returns wrong result
import numpy
def Enquiry(lis1):
    return(numpy.array(lis1))

# Driver Code
lis1 = [0, ]
if Enquiry(lis1):
    print("Not Empty")
else:
    print("Empty")
```

**输出:**

```py
Empty
```

## 正确的 Numpy 方法

1.  如果我们有一个 numpy 数组，那么在所有情况下正确的方法是使用 `if *.size*`。这个 `size` 检查数组的大小，并相应地返回 `True` 或 `False`。
    示例:

```py
# Numpythonic way to check emptiness
# Use of size
import numpy
def Enquiry(lis1):
    return(numpy.array(lis1))

# Driver Code
lis1 = []
if Enquiry(lis1).size:
    print("Not Empty")
else:
    print("Empty")
```

**输出:**

```py
Empty
```

2.  这个例子展示了包含单个 `0` 元素的另一种情况，这在之前的例子中失败了。

```py
# Numpythonic way to check emptiness
# Use of size
import numpy
def Enquiry(lis1):
    return(numpy.array(lis1))

# Driver Code
lis1 = [0, ]
if Enquiry(lis1).size:
    print("Not Empty")
else:
    print("Empty")
```

**输出:**

```py
Not Empty
```

更多参考请访问 [PEP8 风格指南](https://www.python.org/dev/peps/pep-0008/)。