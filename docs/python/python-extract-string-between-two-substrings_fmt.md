# Python：提取两个子字符串之间的字符串

> 原文：[https://www.geeksforgeeks.org/python-extract-string-between-two-substrings/](https://www.geeksforgeeks.org/python-extract-string-between-two-substrings/)

给定一个字符串和两个子字符串，编写一个 Python 程序来提取找到的两个子字符串之间的字符串。

> **输入：**`test_str = "Gfg is best for geeks and CS"`，`sub1 = "is"`，`sub2 = "and"`
>
> **输出：**`best for geeks`
>
> **解释：**`best for geeks` 位于 `is` 和 `and` 之间。
>
> **输入：**`test_str = "Gfg is best for geeks and CS"`，`sub1 = "for"`，`sub2 = "and"`
>
> **输出：**`best`
>
> **解释：**`best` 介于 `for` 和 `and` 之间。

## 方法 1：使用 `index()` + 循环

在这种情况下，我们使用 `index()` 获取两个子字符串的索引，然后使用循环在索引内迭代，以找到它们之间所需的字符串。

```py
# Python3 code to demonstrate working
# of Extract string between 2 substrings
# Using loop + index()

# initializing string
test_str = "Gfg is best for geeks and CS"

# printing original string
print("The original string is : " + str(test_str))

# initializing substrings
sub1 = "is"
sub2 = "and"

# getting index of substrings
idx1 = test_str.index(sub1)
idx2 = test_str.index(sub2)

res = ''
# getting elements in between
for idx in range(idx1 + len(sub1) + 1, idx2):
    res = res + test_str[idx]

# printing result
print("The extracted string : " + res)
```

**输出：**

```py
The original string is : Gfg is best for geeks and CS
The extracted string : best for geeks
```

## 方法 2：使用 `index()` + 字符串切片

类似于上面的方法，只是使用字符串切片来执行切片任务，以提供更紧凑的解决方案。

```py
# Python3 code to demonstrate working
# of Extract string between 2 substrings
# Using index() + string slicing

# initializing string
test_str = "Gfg is best for geeks and CS"

# printing original string
print("The original string is : " + str(test_str))

# initializing substrings
sub1 = "is"
sub2 = "and"

# getting index of substrings
idx1 = test_str.index(sub1)
idx2 = test_str.index(sub2)

# length of substring 1 is added to
# get string from next character
res = test_str[idx1 + len(sub1) + 1: idx2]

# printing result
print("The extracted string : " + res)
```

**输出：**

```py
The original string is : Gfg is best for geeks and CS
The extracted string : best for geeks
```