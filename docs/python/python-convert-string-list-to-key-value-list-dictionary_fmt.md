# Python–将字符串列表转换为键值列表字典

> 原文: [https://www.geeksforgeeks.org/python-convert-string-list-to-key-value-list-dictionary/](https://www.geeksforgeeks.org/python-convert-string-list-to-key-value-list-dictionary/)

给定一个字符串，将其转换为键值列表字典，键作为第一个单词，其余单词作为值列表。

> **输入**: `test_list = ["gfg is best for geeks", "CS is best subject"]`
> **输出**: `{'gfg': ['is', 'best', 'for', 'geeks'], 'CS': ['is', 'best', 'subject']}`
> **解释**: 第 1 个元素与各自剩余的单词配对作为 list。
>
> **输入**: `test_list = ["gfg is best for geeks"]`
> **输出**: `{'gfg': ['is', 'best', 'for', 'geeks']}`
> **解释**: 第 1 个元素与各自剩余的单词配对为 list。

## 方法一: 使用 `split()` + 循环

在本文中，我们对每个字符串进行迭代，然后使用 `split()` 执行字符串的拆分，将第一个元素指定为键，并将其他元素打包到列表中，使用 `*` 运算符并创建键值列表对。

```py
# Python3 code to demonstrate working of
# Convert String List to Key-Value List dictionary
# Using split() + loop

# initializing list
test_list = ["gfg is best for geeks", "I love gfg", "CS is best subject"]

# printing string
print("The original list : " + str(test_list))

res = dict()
for sub in test_list:
    # split() for key
    # packing value list
    key, *val = sub.split()
    res[key] = val

# printing results
print("The key values List dictionary : " + str(res))
```

**输出**

```py
The original list : ['gfg is best for geeks', 'I love gfg', 'CS is best subject']
The key values List dictionary : {'gfg': ['is', 'best', 'for', 'geeks'], 'I': ['love', 'gfg'], 'CS': ['is', 'best', 'subject']}
```

## 方法二: 使用 `split()` + 字典推导式

这是解决这个问题的类似方法。在这种情况下，字典推导式被用来解决这个问题。

```py
# Python3 code to demonstrate working of
# Convert String List to Key-Value List dictionary
# Using split() + dictionary comprehension

# initializing list
test_list = ["gfg is best for geeks", "I love gfg", "CS is best subject"]

# printing string
print("The original list : " + str(test_list))

# using dictionary comprehension to solve this problem
res = {sub[0] : sub[1:] for sub in (ele.split() for ele in test_list)}

# printing results
print("The key values List dictionary : " + str(res))
```

**输出**

```py
The original list : ['gfg is best for geeks', 'I love gfg', 'CS is best subject']
The key values List dictionary : {'gfg': ['is', 'best', 'for', 'geeks'], 'I': ['love', 'gfg'], 'CS': ['is', 'best', 'subject']}
```