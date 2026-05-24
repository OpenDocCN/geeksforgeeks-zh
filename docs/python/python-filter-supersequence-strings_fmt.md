# Python–过滤超序列字符串

> 原文: [https://www.geeksforgeeks.org/python-filter-supersequence-strings/](https://www.geeksforgeeks.org/python-filter-supersequence-strings/)

给定一个字符串列表和子字符串，任务是编写一个 Python 程序来提取所有字符串，这些字符串包含了可以用来生成子字符串的所有字符。

**示例:**

> **输入:** `test_list = ["gfg", "/", "geeksforgeeks", "best", "for", "geeks"]`, `substr = "kgs"`
> **输出:** `["geeks", "geeksforgeeks"]`
> **说明:** 两个字符串中都存在所有 `kgs` 字符。
>
> **输入:** `test_list = ["gfg", "/", "geeksforgeeks", "best", "for", "geeks"]`, `substr = "kgf"`
> **输出:** `["geeksforgeeks"]`
> **说明:** 所有 `kgf` 字符只出现在 `geeksforgeeks` 字符串中。

## 方法一: 使用 `all()` + 列表理解

在本例中，我们使用 `all()` 检查字符串中的所有字符。字符串的迭代是使用列表理解完成的。

```py
# Python3 code to demonstrate working of
# Filter Supersequence Strings
# Using all() + list comprehension

# initializing list
test_list = ["gfg", "/", "geeksforgeeks", "best", "for", "geeks"]

# printing original list
print("The original list is : " + str(test_list))

# initializing substr
substr = "kgs"

# all() checks for all characters in strings
res = [sub for sub in test_list if all(ele in sub for ele in substr)]

# printing result
print("Filtered strings : " + str(res))
```

**输出:**

> The original list is : ['gfg', '/', 'geeksforgeeks', 'best', 'for', 'geeks']
> Filtered strings : ['geeksforgeeks', 'geeks']

## 方法二: 使用 `filter()` + `all()`

在这种情况下，我们使用 `filter()` 和 `lambda` 函数执行过滤任务，而不是在上面的方法中使用列表理解和条件。

```py
# Python3 code to demonstrate working of
# Filter Supersequence Strings
# Using filter() + all()

# initializing list
test_list = ["gfg", "/", "geeksforgeeks", "best", "for", "geeks"]

# printing original list
print("The original list is : " + str(test_list))

# initializing substr
substr = "kgs"

# all() checks for all characters in strings
res = list(filter(lambda sub: all(ele in sub for ele in substr), test_list))

# printing result
print("Filtered strings : " + str(res))
```

**输出:**

> The original list is : ['gfg', '/', 'geeksforgeeks', 'best', 'for', 'geeks']
> Filtered strings : ['geeksforgeeks', 'geeks']