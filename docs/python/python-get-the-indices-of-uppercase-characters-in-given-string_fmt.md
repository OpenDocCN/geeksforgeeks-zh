# Python–获取给定字符串中大写字符的索引

> 原文: [https://www.geeksforgeeks.org/python-get-the-indices-of-uppercase-characters-in-given-string/](https://www.geeksforgeeks.org/python-get-the-indices-of-uppercase-characters-in-given-string/)

给定一个字符串，提取大写字符的索引。

> 输入: `test_str = 'GeeKsFoRGEEks'`
> 输出: `[0, 3, 5, 7, 8]`
> 解释: 返回大写字符的索引。
>
> 输入: `test_str = 'GFG'`
> 输出: `[0, 1, 2]`
> 说明: 全部大写。

## 方法一: 使用列表理解 + `range()` + `isupper()`

在本文中，我们遍历索引直到字符串长度，并使用 `isupper()` 检查大写字符，如果找到，则记录索引。

### Python 3

```py
# Python3 code to demonstrate working of
# Uppercase Indices
# Using list comprehension + range() + isupper()

# initializing string
test_str = 'GeeKsFoRGEEks'

# printing original string
print("The original string is : " + str(test_str))

# Uppercase check using isupper()
res = [idx for idx in range(len(test_str)) if test_str[idx].isupper()]

# printing result
print("Uppercase elements indices : " + str(res))
```

输出

```py
The original string is : GeeKsFoRGEEks
Uppercase elements indices : [0, 3, 5, 7, 8, 9, 10]
```

## 方法 2: 使用 `enumerate()` + `isupper()`

在这种情况下，索引是使用 `enumerate()` 捕获的，`isupper()` 执行与上述方法相同的大写字母检查任务。

### Python 3

```py
# Python3 code to demonstrate working of
# Uppercase Indices
# Using enumerate() + isupper()

# initializing string
test_str = 'GeeKsFoRGEEks'

# printing original string
print("The original string is : " + str(test_str))

# Uppercase check using isupper()
# enumerate() gets indices
res = [idx for idx, chr in enumerate(test_str) if chr.isupper()]

# printing result
print("Uppercase elements indices : " + str(res))
```

输出

```py
The original string is : GeeKsFoRGEEks
Uppercase elements indices : [0, 3, 5, 7, 8, 9, 10]
```