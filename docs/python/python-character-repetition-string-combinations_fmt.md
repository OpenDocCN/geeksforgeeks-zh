# Python – 字符重复字符串组合

> 原文：`https://www.geeksforgeeks.org/python-character-repetition-string-combinations/`

给定一个字符串列表和数字列表，任务是编写一个 Python 程序，通过列表中的每个数字重复每个字符串的每个字符来生成所有可能的字符串。

> **输入：**`test_list = ["gfg", "is", "best"]`, `rep_list = [3, 5, 2]`
> **输出：**`['gggfffggg', 'iiisss', 'bbbeessttt', 'gggggfffffggg', 'iiiiiisssss', 'bbbbbbeeeeesttttt', 'ggffgg', 'iiss', 'bbeesstt']`
> **说明：**将`'gfg'`的每个元素重复 3、5、2 次，输出不同的字符串。
>
> **输入：**`test_list = ["gfg", "is", "best"]`, `rep_list = [3, 1, 2]`
> **输出：**`['gggfffggg', 'is', 'bbbeessttt', 'gfg', 'is', 'best', 'ggffgg', 'iiss', 'bbeesstt']`
> **说明：**将`'gfg'`的每个元素重复 3、1、2 次，输出不同的字符串。

## 方法1：使用 `join()` + 循环 + 列表理解 + `*` 运算符

在这种情况下，构造每个字符串的任务是使用 `join()` 完成的。`*` 运算符执行创建多个字符的任务。嵌套循环用于组合每个数字和每个字符串。

### Python 3

```py
# Python3 code to demonstrate working of
# Character repetition string combinations
# Using join() + nested loop + list comprehension + * operator

# initializing list
test_list = ["gfg", "is", "best"]

# printing original list
print("The original list is : " + str(test_list))

# repeat list
rep_list = [3, 5, 2]

# * operator performs repetitions
# list comprehension encapsulates logic
res = [''.join(sub * ele1 for sub in ele2)
       for ele1 in rep_list for ele2 in test_list]

# printing result
print("All repetition combinations strings : " + str(res))
```

**输出：**

> 原始列表为：`['gfg', 'is', 'best']`
> 所有重复组合字符串：`['gggfffggg', 'iiisss', 'bbbeessttt', 'gggggfffffggg', 'iiiiiisssss', 'bbbbbbeeeeesttttt', 'ggffgg', 'iiss', 'bbeesstt']`

## 方法2：使用 `product()` + `join()` + 循环

在此方法中，通过使用 `product()` 方法避免了用于生成对的嵌套循环。其余所有功能保持与上述方法相同。

### Python 3

```py
# Python3 code to demonstrate working of
# Character repetition string combinations
# Using product() + join() + loop
from itertools import product

# initializing list
test_list = ["gfg", "is", "best"]

# printing original list
print("The original list is : " + str(test_list))

# repeat list
rep_list = [3, 5, 2]

# * operator performs repetitions
# list comprehension encapsulates logic
res = [''.join(sub * ele1 for sub in ele2)
       for ele2, ele1 in product(test_list, rep_list)]

# printing result
print("All repetition combinations strings : " + str(res))
```

**输出：**

> 原始列表为：`['gfg', 'is', 'best']`
> 所有重复组合字符串：`['gggfffggg', 'gggggfffffggg', 'ggffgg', 'iiisss', 'iiiiiisssss', 'iiss', 'bbbeessttt', 'bbbbbbeeeeesttttt', 'bbeesstt']`