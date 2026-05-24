# Python–用数字提取字符串

> 原文: [https://www.geeksforgeeks.org/python-extract-strings-with-a-digit/](https://www.geeksforgeeks.org/python-extract-strings-with-a-digit/)

给定一个字符串列表，提取那些至少有一个数字的字符串。

> **输入**: `test_list = ['gf4g', 'is', 'best', 'gee1ks']`
> **输出**: `['gf4g', 'gee1ks']`
> **解释**: `4`、`1` 为字符串中各自的数字。
>
> **输入**: `test_list = ['gf4g', 'is', 'best', 'geeks']`
> **输出**: `['gf4g']`
> **说明**: `4` 为字符串中的数字。

## 方法一: 使用列表理解 + `any()` + `isdigit()`

在这个迭代中，每个字符串都是使用列表理解完成的，`any()` 和 `isdigit()` 用于检查至少一个数字的任务。

### Python 3

```py
# Python3 code to demonstrate working of
# Extract Strings with a digit
# Using list comprehension + any() + isdigit()

# initializing list
test_list = ['gf4g', 'is', 'best', '4', 'gee1ks']

# printing original list
print("The original list is : " + str(test_list))

# checking if string contain any string using any()
res = [sub for sub in test_list if any(ele for ele in sub if ele.isdigit())]

# printing result
print("Strings with any digit : " + str(res))
```

**输出:**

> 原列表为: `['gf4g', 'is', 'best', '4', 'gee1ks']`
> 任意数字的字符串: `['gf4g', '4', 'gee1ks']`

## 方法二: 使用 `any()` + `filter()` + `lambda`

在本例中，我们使用 `lambda` 和 `filter()` 执行过滤任务，其余部分保持不变。

### Python 3

```py
# Python3 code to demonstrate working of
# Extract Strings with a digit
# Using any() + filter() + lambda

# initializing list
test_list = ['gf4g', 'is', 'best', '4', 'gee1ks']

# printing original list
print("The original list is : " + str(test_list))

# checking if string contain any string using any()
# filter() used to filter strings with digits
res = list(filter(lambda sub: any(
    ele for ele in sub if ele.isdigit()), test_list))

# printing result
print("Strings with any digit : " + str(res))
```

**输出:**

> 原列表为: `['gf4g', 'is', 'best', '4', 'gee1ks']`
> 任意数字的字符串: `['gf4g', '4', 'gee1ks']`