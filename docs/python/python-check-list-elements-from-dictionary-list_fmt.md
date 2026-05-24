# Python：从字典列表中检查列表元素

> 原文：[https://www.geeksforgeeks.org/python-check-list-elements-from-dictionary-list/](https://www.geeksforgeeks.org/python-check-list-elements-from-dictionary-list/)

有时，在处理数据时，我们可能会遇到这样的问题：我们需要检查列表元素是否作为记录列表中的特定键存在。这种问题可能发生在涉及数据的领域，如网络开发和机器学习。让我们讨论解决这个任务的某些方法。

> **输入**：`test_list = [{'Price': 20, 'Color': 'Orange'}, {'Price': 25, 'Color': 'Yellow'}]`
> **输出**：`[True, False, True, False]`
>
> **输入**：`test_list = [{'Color': 'Pink', 'Price': 50}]`
> **输出**：`[False, False, False, False]`

## 方法 1：使用循环

这是解决这个问题的蛮方法。在这种情况下，我们将迭代列表中每个值的所有字典，并与所需的键进行比较，对于拥有它的记录，返回 `True`。

```py
# Python3 code to demonstrate working of
# Check List elements from Dictionary List
# Using loop

# helper function
def check_ele(ele, test_list):
    for sub in test_list:
        for item in sub.values():
            if ele == item:
                return True
    return False

# initializing list
test_list = [{'Name' : 'Apple', 'Price' : 18, 'Color' : 'Red'},
             {'Name' : 'Mango', 'Price' : 20, 'Color' : 'Yellow'},
             {'Name' : 'Orange', 'Price' : 24, 'Color' : 'Orange'},
             {'Name' : 'Plum', 'Price' : 28, 'Color' : 'Red'}]

# printing original list
print("The original list is : " + str(test_list))

# initializing Values list
val_list = ['Yellow', 'Red', 'Orange', 'Green']

# Check List elements from Dictionary List
# Using loop
res = []
for ele in val_list:
    res.append(check_ele(ele, test_list))

# printing result
print("The Association list in Order : " + str(res))
```

**输出：**

> 原列表为：`[{'Name': 'Apple', 'Color': 'Red', 'Price': 18}, {'Name': 'Mango', 'Color': 'Yellow', 'Price': 20}, {'Name': 'Orange', 'Color': 'Orange', 'Price': 24}, {'Name': 'Plum', 'Color': 'Red', 'Price': 28}]`
>
> 关联列表顺序：`[True, True, True, False]`

## 方法 2：使用 `any()` + 生成器表达式

使用 `any()` 并与生成器表达式集成可以解决这个问题。在本文中，我们通过减少内部循环、使用 `any()` 进行测试来减少代码行。

```py
# Python3 code to demonstrate working of
# Check List elements from Dictionary List
# Using any() + generator expression

# initializing list
test_list = [{'Name' : 'Apple', 'Price' : 18, 'Color' : 'Red'},
             {'Name' : 'Mango', 'Price' : 20, 'Color' : 'Yellow'},
             {'Name' : 'Orange', 'Price' : 24, 'Color' : 'Orange'},
             {'Name' : 'Plum', 'Price' : 28, 'Color' : 'Red'}]

# printing original list
print("The original list is : " + str(test_list))

# initializing Values list
val_list = ['Yellow', 'Red', 'Orange', 'Green']

# initializing Key
key = 'Color'

# Check List elements from Dictionary List
# Using loop
res = [any(clr == sub[key] for sub in test_list) for clr in val_list]

# printing result
print("The Association list in Order : " + str(res))
```

**输出：**

> 原列表为：`[{'Name': 'Apple', 'Color': 'Red', 'Price': 18}, {'Name': 'Mango', 'Color': 'Yellow', 'Price': 20}, {'Name': 'Orange', 'Color': 'Orange', 'Price': 24}, {'Name': 'Plum', 'Color': 'Red', 'Price': 28}]`
>
> 关联列表顺序：`[True, True, True, False]`