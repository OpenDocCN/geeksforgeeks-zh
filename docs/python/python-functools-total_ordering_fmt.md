# Python Functools–total_ordering()

> 原文：[https://www.geeksforgeeks.org/python-functools-total_ordering/](https://www.geeksforgeeks.org/python-functools-total_ordering/)

Python 中的 `functools` 模块有助于实现更高阶的函数。高阶函数是调用其他函数的从属函数。`total_ordering` 提供了丰富的类比较方法，有助于比较类，而无需为其显式定义所有函数。所以，这有助于减少代码的冗余。

## 六种富类比较方法为：

*   `object.__lt__(self, other)`
*   `object.__le__(self, other)`
*   `object.__eq__(self, other)`
*   `object.__ne__(self, other)`
*   `object.__gt__(self, other)`
*   `object.__ge__(self, other)`

## 实施这些比较方法有 2 个必要条件：

*   必须从 `__lt__`（小于）、`__le__`（小于或等于）、`__gt__`（大于）或 `__ge__`（大于或等于）中定义至少一种比较方法。
*   还必须定义 `__eq__` 函数。

## 示例：

```py
from functools import total_ordering

@total_ordering
class Students:
    def __init__(self, cgpa):
        self.cgpa = cgpa

    def __lt__(self, other):
        return self.cgpa < other.cgpa

    def __eq__(self, other):
        return self.cgpa == other.cgpa

    def __le__(self, other):
        return self.cgpa <= other.cgpa

    def __ge__(self, other):
        return self.cgpa >= other.cgpa

    def __ne__(self, other):
        return self.cgpa != other.cgpa

Arjun = Students(8.6)
Ram = Students(7.5)

print(Arjun.__lt__(Ram))
print(Arjun.__le__(Ram))
print(Arjun.__gt__(Ram))
print(Arjun.__ge__(Ram))
print(Arjun.__eq__(Ram))
print(Arjun.__ne__(Ram))
```

## 输出

```py
False
False
True
True
False
True
```

## 注：

由于 `__gt__` 方法未执行，显示“未定义”。

## 例 2：

```py
from functools import total_ordering

@total_ordering
class num:
    def __init__(self, value):
        self.value = value

    def __lt__(self, other):
        return self.value < other.value

    def __eq__(self, other):
        # Changing the functionality
        # of equality operator
        return self.value != other.value

# Driver code
print(num(2) < num(3))
print(num(2) > num(3))
print(num(3) == num(3))
print(num(3) == num(5))
```

## 输出：

```py
True
False
False
True
```