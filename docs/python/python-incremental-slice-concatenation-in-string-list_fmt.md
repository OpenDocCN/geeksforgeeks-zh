# Python–字符串列表中的增量切片串联

> 原文：[https://www.geeksforgeeks.org/python-incremental-slice-concatenation-in-string-list/](https://www.geeksforgeeks.org/python-incremental-slice-concatenation-in-string-list/)

给定一个字符串列表，通过增加每个字符串的大小来执行字符串串联的任务。

**示例：**

> **输入**：`test_list = ['gfg', 'for', 'all', 'geek']`
> **输出**：`gfoalgeek`
> **解释**：`g`，`fo`，`all`，`geek` -> 由每个字符串串联而成【递增顺序】。
>
> **输入**：`test_list = ['gfg', 'for', 'geek']`
> **输出**：`gfogee`
> **解释**：`g`，`fo`，`gee` -> 从每个字符串串联【递增顺序】。

## 方法#1：使用循环 + 切片

在这种情况下，使用循环，通过在每次通过时增加计数器的切片来迭代和连接每个字符串。

### Python 3

```py
# Python3 code to demonstrate working of
# Incremental Slice concatenation in String list
# Using loop + slicing

# initializing list
test_list = ['gfg', 'for', 'all', 'geeks']

# printing original list
print("The original list is : " + str(test_list))

res = ''
for idx in range(len(test_list)):

    # Incremental slicing
    res += test_list[idx][:idx + 1]

# printing result
print("Incremental sliced concatenated string : " + str(res))
```

**输出**

```py
The original list is : ['gfg', 'for', 'all', 'geeks']
Incremental sliced concatenated string : gfoallgeek
```

## 方法2：使用 `join()` + 列表推导式

在这种情况下，连接任务使用 `join()` 完成，迭代任务使用列表推导式来提供速记。

### Python 3

```py
# Python3 code to demonstrate working of
# Incremental Slice concatenation in String list
# Using join() + list comprehension

# initializing list
test_list = ['gfg', 'for', 'all', 'geeks']

# printing original list
print("The original list is : " + str(test_list))

# join performs concatenation
res = ''.join([test_list[idx][:idx + 1] for idx in range(len(test_list))])

# printing result
print("Incremental sliced concatenated string : " + str(res))
```

**输出**

```py
The original list is : ['gfg', 'for', 'all', 'geeks']
Incremental sliced concatenated string : gfoallgeek
```