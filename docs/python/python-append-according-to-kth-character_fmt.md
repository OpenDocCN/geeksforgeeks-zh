# Python–根据第Kth个字符追加

> 原文: [https://www.geeksforgeeks.org/python-append-according-to-kth-character/](https://www.geeksforgeeks.org/python-append-according-to-kth-character/)

给定一个字符串列表，根据第Kth个索引值追加到字符串`i`或`j`值。

> **输入**: `test_list = ["geeksforgeeks", "best", "for", "geeks"]`, `K = 2`, `N = 'e'`, `i, j = "..", "@@"`
> **输出**: `["geeksforgeeks..", "best@@", "for@@", "geeks.."]`
> **解释**: `geeks`和`geeks`拥有相似的第二occ.值为`'e'`，因此会附加`".."`。
>
> **输入**: `test_list = ["giiksforgeeks", "bst", "for", "geeks"]`, `K = 2`, `N = 'e'`, `i, j = "..", "@@"`
> **输出**: `['giiksforgeeks@@', 'best@@', 'for@@', 'geeks@@']`
> **解释**: 没有`K`值为`'e'`的值，全部附加`@@`。

## 方法#1: 使用循环

这是解决这个问题的暴力方法，我们检查每个字符串的`Kth`索引，如果发现是`N`，那么`i`值被追加，否则`j`被追加。

### 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Append according to Kth character
# Using loop

# initializing lists
test_list = ["geeksforgeeks", "best", "for", "geeks"]

# printing string
print("The original list : " + str(test_list))

# initializing K
K = 2

# initializing N
N = 'e'

# initializing i, j
i, j = "**", "##"

res = []
for sub in test_list:

    # checking for Kth index to be N
    if sub[K] == N:
        res.append(sub + i)
    else:
        res.append(sub + j)

# printing results
print("The resultant List : " + str(res))
```

**Output**

```py
The original list : ['geeksforgeeks', 'best', 'for', 'geeks']
The resultant List : ['geeksforgeeks**', 'best##', 'for##', 'geeks**']
```

## 方法 2: 使用列表理解

这以类似的方式解决了这个问题，不同的是，这是一个简写，可以作为解决这个问题的一个线性方法。

### 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Append according to Kth character
# Using list comprehension

# initializing lists
test_list = ["geeksforgeeks", "best", "for", "geeks"]

# printing string
print("The original list : " + str(test_list))

# initializing K
K = 2

# initializing N
N = 'e'

# initializing i, j
i, j = "**", "##"

# shorthand to solve this problem
res = [sub + i if sub[K] == N else sub + j for sub in test_list]

# printing results
print("The resultant List : " + str(res))
```

**Output**

```py
The original list : ['geeksforgeeks', 'best', 'for', 'geeks']
The resultant List : ['geeksforgeeks**', 'best##', 'for##', 'geeks**']
```