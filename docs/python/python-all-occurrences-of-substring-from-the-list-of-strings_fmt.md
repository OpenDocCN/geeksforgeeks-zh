# Python – 字符串列表中出现的所有子字符串

> 原文: [https://www.geeksforgeeks.org/python-all-occurrences-of-substring-from-the-list-of-strings/](https://www.geeksforgeeks.org/python-all-occurrences-of-substring-from-the-list-of-strings/)

给定字符串列表和子字符串列表。任务是从字符串列表中提取所有出现的子字符串。

**示例:**

> **输入**: `test_list = ["gfg is best", "gfg is good for CS", "gfg is recommended for CS"]`
> `subs_list = ["gfg", "CS"]`
> **输出**: `['gfg is good for CS', 'gfg is recommended for CS']`
> **说明**: 结果字符串同时有“gfg”和“CS”。
> **输入**: `test_list = ["gfg is best", "CS recommended gfg"]`
> `subs_list = ["gfg"]`
> **输出**: `["gfg is best", "CS recommended gfg"]`
> **说明**: 结果字符串有“gfg”。

## 方法1：使用循环 + in 运算符

上述功能的组合可以用来解决这个问题。在这种情况下，我们运行一个循环来提取列表中的所有字符串以及所有子字符串。`in` 运算符用于检查子字符串是否存在。

### Python 3

```py
# Python3 code to demonstrate working of
# Strings with all Substring Matches
# Using loop + in operator

# initializing list
test_list = ["gfg is best", "gfg is good for CS",
             "gfg is recommended for CS"]

# printing original list
print("The original list is : " + str(test_list))

# initializing Substring List
subs_list = ["gfg", "CS"]

res = []
for sub in test_list:
    flag = 0
    for ele in subs_list:
        # checking for non existence of
        # any string
        if ele not in sub:
            flag = 1
            break
    if flag == 0:
        res.append(sub)

# printing result
print("The extracted values : " + str(res))
```

**输出:**

> 原列表为: `['gfg is best', 'gfg is good for CS', 'gfg is recommended for CS']`
> 抽取值: `['gfg is good for CS', 'gfg is recommended for CS']`

## 方法2：使用 all() + 列表推导式

这是一种单行方法，在它的帮助下，我们可以完成这项任务。在这种情况下，我们使用 [`all()`](https://www.geeksforgeeks.org/any-all-in-python/) 检查所有值的存在性，并使用列表推导式来迭代所有容器。

### Python 3

```py
# Python3 code to demonstrate working of
# Strings with all Substring Matches
# Using all() + list comprehension

# initializing list
test_list = ["gfg is best", "gfg is good for CS",
             "gfg is recommended for CS"]

# printing original list
print("The original list is : " + str(test_list))

# initializing Substring List
subs_list = ["gfg", "CS"]

# using all() to check for all values
res = [sub for sub in test_list
       if all((ele in sub) for ele in subs_list)]

# printing result
print("The extracted values : " + str(res))
```

**输出:**

> 原列表为: `['gfg is best', 'gfg is good for CS', 'gfg is recommended for CS']`
> 抽取值: `['gfg is good for CS', 'gfg is recommended for CS']`