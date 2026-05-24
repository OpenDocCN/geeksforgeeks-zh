# Python – K 差连续元素

> 原文: [https://www.geeksforgeeks.org/python-k-difference-consecutive-elements/](https://www.geeksforgeeks.org/python-k-difference-consecutive-elements/)

给定一个整数元素列表，检查每个元素与连续元素的差值是否为 `k`。

> **输入**: `test_list = [5, 6, 3, 2, 5, 3, 4]`, `K = 1`
> **输出**: `[True, False, True, False, False, True]`
> **解释**: 5、6；3, 2；和 3、4 之间有 1 个差异。
>
> **输入**: `test_list = [5, 6, 3, 2, 5, 3, 4]`, `K = 2`
> **输出**: `[False, False, False, False, True, False]`
> **解释**: 只有 5，3 之间有 2 个差异。

## 方法一: 使用列表理解

这是执行这项任务的方法之一。在这种情况下，我们用下一个元素检查每个元素，如果差是 `K`，那么我们标记它为 `True`，否则为 `False`。

### Python 3

```py
# Python3 code to demonstrate working of
# K difference Consecutive elements
# Using list comprehension

# initializing list
test_list = [5, 6, 3, 2, 5, 3, 4]

# printing original list
print("The original list : " + str(test_list))

# initializing K
K = 3

# using list comprehension and abs() to compute result
res = [True if abs(test_list[idx] - test_list[idx + 1]) == K else False
       for idx in range(len(test_list) - 1)]

# printing result
print("The difference list result : " + str(res))
```

**Output**

```py
The original list : [5, 6, 3, 2, 5, 3, 4]
The difference list result : [False, True, False, True, False, False]
```

## 方法二: 使用 `zip()` + 列表理解

这是执行该任务的另一种方式。在这种情况下，连续的列表使用 `zip()` 进行配对，计算贯穿列表理解。

### Python 3

```py
# Python3 code to demonstrate working of
# K difference Consecutive elements
# Using zip() + list comprehension

# initializing list
test_list = [5, 6, 3, 2, 5, 3, 4]

# printing original list
print("The original list : " + str(test_list))

# initializing K
K = 3

# using list comprehension and abs() to compute result
# zip() used to pair Consecutive elements list
res = [abs(a - b) == K for a, b in zip(test_list, test_list[1:])]

# printing result
print("The difference list result : " + str(res))
```

**Output**

```py
The original list : [5, 6, 3, 2, 5, 3, 4]
The difference list result : [False, True, False, True, False, False]
```