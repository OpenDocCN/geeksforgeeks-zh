# Python–过滤第二个列表中索引包含给定子字符串的字符串列表

> 原文: [https://www.geeksforgeeks.org/python-filter-the-list-of-string-whose-index-in-second-list-contains-the-given-substring/](https://www.geeksforgeeks.org/python-filter-the-list-of-string-whose-index-in-second-list-contains-the-given-substring/)

给定两个列表，从第一个列表中提取所有元素，第二个列表中对应的索引包含所需的子字符串。

**示例:**

> **输入**: `test_list1 = ["Gfg", "is", "not", "best", "and", "not", "CS"]`, `test_list2 = ["it ok", "all ok", "错了", "看起来还行", "ok", "错了", "那还行"]`, `sub_str = "ok"`
> **输出**: `["Gfg", "is", "best", "and", "CS"]`
> **解释**: 所有保留的都包含“ok”作为对应 idx 中的子串，例如: Gfg - 【Tt】
>
> **输入**: `test_list1 = ["Gfg", "not", "best"]`, `test_list2 = ["yes", "noo", "its yes"]`, `sub_str = "yes"`
> **输出**: `['Gfg', 'best']`
> **说明:** 所有保留的都包含“yes”作为对应 idx 中的子串，例如: Gfg -> yes ( has yes)作为子串。

**方法#1: 使用 `zip()` + `loop` + `in` 运算符**

在本文中，我们使用 `zip()` 组合索引，`in` 运算符用于检查子字符串。循环用于迭代的任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Extract elements filtered by substring
# from other list Using zip() + loop + in
# operator

# initializing list
test_list1 = ["Gfg", "is", "not", "best", "and",
              "not", "for", "CS"]
test_list2 = ["Its ok", "all ok", "wrong", "looks ok",
              "ok", "wrong", "ok", "thats ok"]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# initializing substr
sub_str = "ok"

res = []
# using zip() to map by index
for ele1, ele2 in zip(test_list1, test_list2):

    # checking for substring
    if sub_str in ele2:
        res.append(ele1)

# printing result
print("The extracted list : " + str(res))
```

**输出:**

> 原列表 1 为: ['Gfg', 'is', 'not', 'best', 'and', 'not', 'for', 'CS']
> 原列表 2 为: ['it ok', 'all ok', 'error', 'looks', 'ok', 'error', 'ok', 'thank ok']
> 提取的列表: ['Gfg', 'is', 'best', 'and', 'for', 'CS']

**方法 2: 使用列表理解+ `zip()`**

这类似于上面的方法。这里唯一的区别是列表理解被用作解决问题的速记。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Extract elements filtered by substring
# from other list Using list comprehension + zip()

# initializing list
test_list1 = ["Gfg", "is", "not", "best", "and",
              "not", "for", "CS"]
test_list2 = ["Its ok", "all ok", "no", "looks ok",
              "ok", "wrong", "ok", "thats ok"]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# initializing substr
sub_str = "ok"

# using list comprehension to perform task
res = [ele1 for ele1, ele2 in zip(test_list1, test_list2) if sub_str in ele2]

# printing result
print("The extracted list : " + str(res))
```

**输出:**

> 原列表 1 为: ['Gfg', 'is', 'not', 'best', 'and', 'not', 'for', 'CS']
> 原列表 2 为: ['it ok', 'all ok', 'no', 'looks', 'ok', 'error', 'ok', 'thank ok']
> 提取的列表: ['Gfg', 'is', 'best', 'and', 'for', 'CS']