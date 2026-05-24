# 区别 `!=` 和 `is not` 运算符在 Python 中

> 原文: [https://www.geeksforgeeks.org/difference-between-and-is-not-operator-in-python/](https://www.geeksforgeeks.org/difference-between-and-is-not-operator-in-python/)

在这篇文章中，我们将看到 `!=` (不相等) 运算符。在 Python 中，`!=` 定义为“不等于”运算符。如果两边的操作数不相等，则返回 `True`，如果相等，则返回 `False`。而 `is not` 操作员检查两个对象的 `id()` 是否相同。如果相同，则返回 `False`，如果不相同，则返回 `True`。`is not` 运算符在两边的操作数不相等时返回 `True`，相等时返回 `False`。

让我们逐一了解概念：

## 例 1

```py
a = 10
b = 10

print(a is not b)
print(id(a), id(b))

c = "Python"
d = "Python"
print(c is not d)
print(id(c), id(d))

e = [1,2,3,4]
f = [1,2,3,4]
print(e is not f)
print(id(e), id(f))
```

**输出：**

```py
False
140733278626480 140733278626480
False
2693154698864 2693154698864
True
2693232342792 2693232342600
```

**说明：**

1.  首先，对于整数数据，输出为 `False`，因为变量 `a` 和 `b` 都引用相同的数据 `10`。
2.  其次，对于字符串数据，输出为 `False`，因为变量 `c`、`d` 都引用了相同的数据 `"Python"`。
3.  第三，对于列表数据，输出为 `True`，因为变量 `e`，`f` 有不同的内存地址。(即使两个变量具有相同的数据)

## 例 2

`!=` 定义为“不等于”运算符。如果两边的操作数不相等，则返回 `True`，如果相等，则返回 `False`。

```py
# Python3 code to
# illustrate the
# difference between
# != and is operator

a = 10
b = 10
print(a != b)
print(id(a), id(b))

c = "Python"
d = "Python"
print(c != d)
print(id(c), id(d))

e = [ 1, 2, 3, 4]
f=[ 1, 2, 3, 4]
print(e != f)
print(id(e), id(f))
```

**输出：**

```py
False
140733278626480 140733278626480
False
2693154698864 2693154698864
False
2693232369224 2693232341064
```

## 例 3

`!=` 运算符比较两个对象的值或相等性，而 Python `is not` 运算符检查两个变量是否指向内存中的同一个对象。

```py
# Python3 code to
# illustrate the
# difference between
# != and is not operator
# [] is an empty list
list1 = []
list2 = []
list3 = list1

#First if
if (list1 != list2):
    print(" First if Condition True")
else:
    print("First else Condition False")

#Second if
if (list1 is not list2):
    print("Second if Condition True")
else:
    print("Second else Condition  False")

#Third if
if (list1 is not list3):
    print("Third if Condition True")
else:
    print("Third else Condition False")

list3 = list3 + list2

#Fourth if
if (list1 is not list3):
    print("Fourth if Condition True")
else:
    print("Fourth else Condition False")
```

**输出：**

```py
First else Condition False
Second if Condition True
Third else Condition False
Fourth if Condition True
```

**说明：**

1.  第一个 `if` 条件输出为 `False`，因为 `list1` 和 `list2` 都是空列表。
2.  第二个 `if` 条件显示为 `True`，因为两个空列表位于不同的内存位置。因此，`list1` 和 `list2` 引用不同的对象。我们可以用 Python 中的 `id()` 函数来检查它，该函数返回一个对象的“标识”。
3.  第三个 `if` 的输出为 `False`，因为 `list1` 和 `list3` 都指向同一对象。
4.  第四个 `if` 的输出为 `True`，因为两个列表的串联总是产生一个新列表。