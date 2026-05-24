# Python – 找出列表中大于每个元素的数字出现频率

> 原文：[https://www.geeksforgeeks.org/python-find-the-frequency-of-numbers-greater-than-each-element-in-a-list/](https://www.geeksforgeeks.org/python-find-the-frequency-of-numbers-greater-than-each-element-in-a-list/)

给定一个列表，构造一个新列表，其元素的频率大于或等于该列表，对应于该列表的每个元素。

> **输入**：`test_list = [6, 3, 7, 1, 2, 4]`
> **输出**：`[2, 4, 1, 6, 5, 3]`
> **解释**：列表中 6、7 大于等于 6，因此为 2。
> **输入**：`test_list = [6, 3, 7]`
> **输出**：`[2, 3, 1]`
> **解释**：列表中 6，7 大于等于 6，因此为 2。

## 方法一：利用 `sum()` 和列表推导式

这里，嵌套列表推导式用于访问列表的每个元素，`sum()` 用于获取大于或等于索引元素的元素的总和。

```py
# initializing list
test_list = [6, 3, 7, 1, 2, 4]

# printing original list
print("The original list is : " + str(test_list))

# sum() performs counts of element which are Greater or equal to
res = [sum(1 for ele in test_list if sub <= ele) for sub in test_list]

# printing result
print("Greater elements Frequency list : " + str(res))
```

**输出：**

> 原来的名单是：[6, 3, 7, 1, 2, 4]
>
> 更大的元素频率列表：[2, 4, 1, 6, 5, 3]

## 方法二：使用 `sorted()`、`bisect_left()` 和列表推导式

在本例中，我们使用 `bisect_left()` 获得小于元素的元素。然后，从总长度中减去这样得到的数字，我们就得到大于元素的元素数。

```py
# import module
import bisect

# initializing list
test_list = [6, 3, 7, 1, 2, 4]

# printing original list
print("The original list is : " + str(test_list))

# sorting before bisect
temp = sorted(test_list)

# getting total greater elements for each element
res = [len(test_list) - bisect.bisect_left(temp, ele) for ele in test_list]

# printing result
print("Greater elements Frequency list : " + str(res))
```

**输出：**

> 原来的名单是：[6, 3, 7, 1, 2, 4]
>
> 更大的元素频率列表：[2, 4, 1, 6, 5, 3]