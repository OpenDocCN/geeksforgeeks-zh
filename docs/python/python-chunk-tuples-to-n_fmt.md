# Python | 将元组分块为N个一组

> 原文: [https://www.geeksforgeeks.org/python-chunk-tuples-to-n/](https://www.geeksforgeeks.org/python-chunk-tuples-to-n/)

有时，在处理数据时，我们可能会遇到需要将元组按大小 `N` 进行分块的问题。这在需要分块提供数据的应用程序中很常见。让我们讨论执行这项任务的某些方法。

## 方法一：使用列表推导式

这是执行这个任务的直接且简洁的方法。在这种情况下，我们一次拆分 `N` 个元素，并为它们构建一个新的元组。

```py
# Python3 code to demonstrate working of
# Chunk Tuples to N
# using list comprehension

# initialize tuple
test_tup = (10, 4, 5, 6, 7, 6, 8, 3, 4)

# printing original tuple
print("The original tuple : " + str(test_tup))

# initialize N
N = 3

# Chunk Tuples to N
# using list comprehension
res = [test_tup[i : i + N] for i in range(0, len(test_tup), N)]

# printing result
print("The tuples after chunking are : " + str(res))
```

**输出：**

```py
The original tuple : (10, 4, 5, 6, 7, 6, 8, 3, 4)
The tuples after chunking are : [(10, 4, 5), (6, 7, 6), (8, 3, 4)]
```

## 方法二：使用 `zip()` 与 `iter()`

以上功能的组合也可以用来解决这个问题。在本文中，我们使用 `zip()` 来组合组块，`iter()` 转换成合适的格式。

```py
# Python3 code to demonstrate working of
# Chunk Tuples to N
# using zip() + iter()

# initialize tuple
test_tup = (10, 4, 5, 6, 7, 6, 8, 3, 4)

# printing original tuple
print("The original tuple : " + str(test_tup))

# initialize N
N = 3

# Chunk Tuples to N
# using zip() + iter()
temp = [iter(test_tup)] * N
res = list(zip(*temp))

# printing result
print("The tuples after chunking are : " + str(res))
```

**输出：**

```py
The original tuple : (10, 4, 5, 6, 7, 6, 8, 3, 4)
The tuples after chunking are : [(10, 4, 5), (6, 7, 6), (8, 3, 4)]
```