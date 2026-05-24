# Python：从列表列表中过滤仅包含字母的行

> 原文：[https://www.geeksforgeeks.org/python-filter-rows-with-only-alphabets-from-list-of-lists/](https://www.geeksforgeeks.org/python-filter-rows-with-only-alphabets-from-list-of-lists/)

给定矩阵，编写一个 Python 程序来提取字符串中只包含字母的行。

**示例：**

> **输入**：`test_list = [["Gfg", "is", "best"], ["geeks4geeks", "good"], ["Gfg good"], ["love", "Gfg"]]`
> **输出**：`[['Gfg', 'is', 'best'], ['love', 'Gfg']]`
> **说明**：提取所有只有字母的字符串。
>
> **输入**：`test_list = [["gfg", "is", "!best"], ["Geeks4Geeks", "good"], ["Gfg good"], ["love", "Gfg"]]`
> **输出**：`[['love', 'gfg']]`
> **解释**：提取所有只含字母的字符串。

## 方法#1：使用 `isalpha()` + `all()` + 列表推导式

在本例中，我们使用 `isalpha()` 检查所有字母，使用 `all()` 确保所有字符串只包含字母。列表推导式用于遍历行。

### Python 3

```py
# Python3 code to demonstrate working of
# Filter rows with only Alphabets
# Using isalpha() + all() + list comprehension

# initializing list
test_list = [["gfg", "is", "best"], ["Geeks4Geeks", "good"],
             ["Gfg is good"], ["love", "gfg"]]

# printing original lists
print("The original list is : " + str(test_list))

# all() checks for all strings to contain alphabets
res = [sub for sub in test_list if all(ele.isalpha() for ele in sub)]

# printing result
print("Filtered Rows : " + str(res))
```

**输出：**

> 原列表为：`[['gfg', 'is', 'best'], ['Geeks4Geeks', 'good'], ['Gfg is good'], ['love', 'gfg']]`
> 过滤行：`[['gfg', 'is', 'best'], ['love', 'gfg']]`

## 方法#2：使用 `filter()` + `lambda` + `join()` + `isalpha()`

在本文中，我们使用 `join()` 连接每个字符串，并使用 `isalpha()` 测试它的所有字母，如果判断结果为真，则添加。

### Python 3

```py
# Python3 code to demonstrate working of
# Filter rows with only Alphabets
# Using filter() + lambda + join() + isalpha()

# initializing list
test_list = [["gfg", "is", "best"], ["Geeks4Geeks", "good"],
             ["Gfg is good"], ["love", "gfg"]]

# printing original lists
print("The original list is : " + str(test_list))

# join() used to concatenate strings
res = list(filter(lambda sub: ''.join(
    [ele for ele in sub]).isalpha(), test_list))

# printing result
print("Filtered Rows : " + str(res))
```

**输出：**

> 原列表为：`[['gfg', 'is', 'best'], ['Geeks4Geeks', 'good'], ['Gfg is good'], ['love', 'gfg']]`
> 过滤行：`[['gfg', 'is', 'best'], ['love', 'gfg']]`