# Python – 在 ASCII 范围内过滤字符串

> 原文: [https://www.geeksforgeeks.org/python-filter-strings-within-ascii-range/](https://www.geeksforgeeks.org/python-filter-strings-within-ascii-range/)

给定 ASCII 或字母范围，过滤特定范围内的字符串。

> **输入**: `test_list = ["gfg", "is", "best", "for", "geeks"]`, `strt_asc`, `end_asc = 105, 115`
> **输出**: `['is']`
> **解释**: `i` 有 105，`s` 有 115，在 ASCII 值范围内。
> **输入**: `test_list = ["gfg", "is", "best", "for", "geeks"]`, `strt_asc`, `end_asc = 100, 115`
> **输出**: `["gfg", "is", "for", "geeks"]`
> **解释**: 包含范围字符的字符串。

## 方法一：使用列表推导式 + `all()` + `ord()`

在这种情况下，我们检查所有字符是否在给定的 ASCII 范围内，使用 `ord()` 计算，并相应地过滤字符串。

### Python 3

```py
# Python3 code to demonstrate working of
# Filter Strings within ASCII range
# Using list comprehension + ord() + all()

# initializing list
test_list = ["gfg", "is", "best", "for", "geeks"]

# printing original list
print("The original list is : " + str(test_list))

# initializing ASCII range
strt_asc, end_asc = 105, 115

# checking for all characters to be in ASCII range
res = [sub for sub in test_list if all(
    ord(ele) >= strt_asc and ord(ele) <= end_asc for ele in sub)]

# printing result
print("Filtered Strings : " + str(res))
```

**输出**

```py
The original list is : ['gfg', 'is', 'best', 'for', 'geeks']
Filtered Strings : ['is']
```

## 方法二：使用 `filter()` + `lambda` + `all()` + `ord()`

在本例中，我们使用 `filter()` 和 `lambda` 函数执行过滤任务，`ord()` 和 `all()` 的使用方式与上述方法类似。

### Python 3

```py
# Python3 code to demonstrate working of
# Filter Strings within ASCII range
# Using filter() + lambda + all() + ord()

# initializing list
test_list = ["gfg", "is", "best", "for", "geeks"]

# printing original list
print("The original list is : " + str(test_list))

# initializing ASCII range
strt_asc, end_asc = 105, 115

# checking for all characters to be in ASCII range
res = list(filter(lambda sub: all(ord(ele) >= strt_asc and ord(
    ele) <= end_asc for ele in sub), test_list))

# printing result
print("Filtered Strings : " + str(res))
```

**输出**

```py
The original list is : ['gfg', 'is', 'best', 'for', 'geeks']
Filtered Strings : ['is']
```