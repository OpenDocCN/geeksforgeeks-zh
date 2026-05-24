# 如何在 Python 中检查一个集合是否包含元素？

> 原文: [https://www.geeksforgeeks.org/how-to-check-if-a-set-contains-an-element-in-python/](https://www.geeksforgeeks.org/how-to-check-if-a-set-contains-an-element-in-python/)

在本文中，我们将讨论如何在 Python 中检查一个集合是否包含元素。

## 方法 1: 使用 `in` 运算符

这是一个成员运算符，用于检查给定值是否存在于集合中。如果给定元素存在于集合中，它将返回 `True`，否则返回 `False`。

**语法**:

```py
element in set
```

其中

*   `set` 是一个输入集合
*   `element` 是要检查的值

**示例**: 检查集合中是否存在元素

### Python 3

```py
# import random module
import random

# create a set with integer elements
data = {7058, 7059, 7072, 7074, 7076}

# check 7058
print(7058 in data)

# check 7059
print(7059 in data)

# check 7071
print(7071 in data)
```

**输出**:

```py
True
True
False
```

## 方法 2: 使用 `not in` 运算符

这是一个成员运算符，用于检查给定值是否存在于集合中。如果给定元素不在集合中，它将返回 `True`，否则返回 `False`。

**语法**:

```py
element not in set
```

其中，

*   `set` 是一个输入集合
*   `element` 是要检查的值

**示例**: 检查集合中是否存在元素

### Python 3

```py
# import random module
import random

# create a set with integer elements
data = {7058, 7059, 7072, 7074, 7076}

# check 7058
print(7058 not in data)

# check 7059
print(7059 not in data)

# check 7071
print(7071 not in data)
```

**输出**:

```py
False
False
True
```