# 字典按值排序和反向按值排序的不同方式

> 原文: [https://www.geeksforgeeks.org/different-ways-of-sorting-dictionary-by-values-and-reverse-sorting-by-values/](https://www.geeksforgeeks.org/different-ways-of-sorting-dictionary-by-values-and-reverse-sorting-by-values/)

**先决条件:** [Python 词典](https://www.geeksforgeeks.org/python-dictionary/)

字典是一个无序的、可变的和有索引的集合。在 [Python](https://www.geeksforgeeks.org/python-programming-language/) 中，字典是用花括号写的，有键和值。我们可以使用键访问字典的值。本文讨论了 10 种不同的按值对 Python 字典进行排序的方法，以及按值进行反向排序的方法。

## 使用 lambda 函数与 items() 和 sorted()

使用 [lambda 函数](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/) 返回特定项元组的键（第 0 个元素），当这些被传递到 [`sorted()` 方法](https://www.geeksforgeeks.org/sorted-function-python/) 时，它返回一个排序的序列，然后将该序列[类型转换到字典](https://www.geeksforgeeks.org/python-type-conversion-of-dictionary-items/)中。 [`keys()`](https://www.geeksforgeeks.org/python-get-dictionary-keys-as-a-list/) 方法返回一个视图对象，该对象显示字典中所有键的列表。 [`sorted()`](https://www.geeksforgeeks.org/python-sort-python-dictionaries-by-key-or-value/) 用于对字典的关键字进行排序。

**示例:**

> **输入:** `my_dict = {2: 'three', 1: 'two'}`
> **输出:** `[(2, 'three'), (1, 'two')]`

下面是使用 lambda 函数的实现:

```py
# Python program to sort dictionary
# by value using lambda function

# Initialize a dictionary
my_dict = {2: 'three',
           1: 'two'}

# Sort the dictionary
sorted_dict = sorted(
  my_dict.items(),
  key = lambda kv: kv[1])

# Print sorted dictionary
print("Sorted dictionary is :",
      sorted_dict)
```

**Output**

```py
Sorted dictionary is : [(2, 'three'), (1, 'two')]
```

## 单独使用 items()

方法 [`items()`](https://www.geeksforgeeks.org/python-dictionary-items-method/) 单独使用 `key` 和 `value` 两个变量按值对字典进行排序。

**示例:**

> **输入:** `my_dict = {'c': 3, 'a': 1, 'd': 4, 'b': 2}`
> **输出:** `[(1, 'a'), (2, 'b'), (3, 'c'), (4, 'd')]`

下面是使用方法 `items()` 的实现:

```py
# Python program to sort dictionary
# by value using item function

# Initialize a dictionary
my_dict = {'c': 3,
           'a': 1,
           'd': 4,
           'b': 2}

# Sorting dictionary
sorted_dict = sorted([(value, key)
 for (key, value) in my_dict.items()])

# Print sorted dictionary
print("Sorted dictionary is :")
print(sorted_dict)
```

**Output**

```py
Sorted dictionary is :
[(1, 'a'), (2, 'b'), (3, 'c'), (4, 'd')]
```

## 使用 sorted() 和 get()

方法 [`get()`](https://www.geeksforgeeks.org/get-method-dictionaries-python/) 返回给定键的值（如果存在于字典中）。如果没有，则返回 `None`。

**示例:**

> **输入:** `my_dict = {'red': '#FF0000', 'green': '#008000', 'black': '#000000', 'white': '#FFFFFF'}`
> **输出:**
> `black #000000`
> `green #008000`
> `red #FF0000`
> `white #FFFFFF`

下面是使用 `sorted()` 和 `get()` 方法的实现:

```py
# Python program to sort dictionary
# by value using sorted() and get()

# Initialize a dictionary
my_dict = {'red': '#FF0000', 'green': '#008000',
           'black': '#000000', 'white': '#FFFFFF'}

# Sort and print dictionary
print("Sorted dictionary is :")
for w in sorted(my_dict, key = my_dict.get):
    print(w, my_dict[w])
```

**Output**

```py
Sorted dictionary is :
black #000000
green #008000
red #FF0000
white #FFFFFF
```

## 使用 operator 模块的 itemgetter

方法 `itemgetter(n)` 构造一个可调用的，假定一个可迭代的对象作为输入，并从中取出第 `n` 个元素。

**示例**

> **输入:**
> `my_dict = {'a': 23, 'g': 67, 'e': 12, 45: 90}`
> **输出:**
> `[('e', 12), ('a', 23), ('g', 67), (45, 90)]`

下面是使用 `itemgetter()` 对字典进行排序的 python 程序:

```py
# Python program to sort dictionary
# by value using itemgetter() function

# Importing operator
import operator

# Initialize a dictionary
my_dict = {'a': 23,
           'g': 67,
           'e': 12,
           45: 90}

# Sorting dictionary
sorted_dict = sorted(my_dict.items(),
             key = operator.itemgetter(1))

# Printing sorted dictionary
print("Sorted dictionary is :")
print(sorted_dict)
```

**Output**

```py
Sorted dictionary is :
[('e', 12), ('a', 23), ('g', 67), (45, 90)]
```

## 使用 collections 中的 OrderedDict

[`OrderedDict`](https://www.geeksforgeeks.org/ordereddict-in-python/) 是一个标准库类，位于 [`collections`](https://www.geeksforgeeks.org/python-collections-module/) 模块中。`OrderedDict` 维护插入的键的顺序。

**示例:**

> **输入:** `my_dict = {1: 2, 3: 4, 4: 3, 2: 1, 0: 0}`
> **输出:** `[(0, 0), (2, 1), (1, 2), (4, 3), (3, 4)]`

下面是使用有序字典的实现:

```py
# Python program to sort dictionary
# by value using OrderedDict

# Import OrderedDict
from collections import OrderedDict

# Initialize a dictionary
my_dict = {1: 2, 3: 4, 4: 3, 2: 1, 0: 0}

# Sort dictionary
sorted_dict = OrderedDict(sorted(
  my_dict.items(), key = lambda x: x[1]))

# Print the sorted dictionary
print("Sorted dictionary is :")
print(sorted_dict)
```

**Output**

```py
Sorted dictionary is :
OrderedDict([(0, 0), (2, 1), (1, 2), (4, 3), (3, 4)])
```

## 使用 collections 中的 Counter

[`Counter`](https://www.geeksforgeeks.org/python-counter-objects-elements/) 是一个无序集合，其中元素作为 `dict` 键存储，它们的计数作为 `dict` 值。`Counter` 元素计数可以是正整数、零或负整数。

**示例:**

> **输入:** `my_dict = {'hello': 1, 'python': 5, 'world': 3}`
> **输出:** `[('hello', 1), ('world', 3), ('python', 5)]`

下面是使用 `collections` 中的 `Counter` 的实现:

```py
# Python program to sort dictionary
# by value using Counter

# Import Counter
from collections import Counter

# Initialize a dictionary
my_dict = {'hello': 1, 'python': 5, 'world': 3}

# Sort and print the dictionary
sorted_dict = Counter(my_dict)
print("Sorted dictionary is :")
print(sorted_dict.most_common()[::-1])
```

**Output**

```py
Sorted dictionary is :
[('hello', 1), ('world', 3), ('python', 5)]
```

## 按值反向排序字典

升序和降序排序的语法相同。对于反向排序，想法是使用 `reverse=True` 参数和 `sorted()` 函数。

**示例:**

> **输入:**
> `my_dict = {'red': '#FF0000', 'green': '#008000', 'black': '#000000', 'white': '#FFFFFF'}`
> **输出:**
> `white #FFFFFF`
> `red #FF0000`
> `green #008000`
> `black #000000`

下面是使用按值反向排序字典的实现:

```py
# Python program to sort dictionary
# by value using sorted setting
# reverse parameter to true

# Initialize a dictionary
my_dict = {'red': '#FF0000', 'green': '#008000',
           'black': '#000000', 'white': '#FFFFFF'}

# Sort and print the dictionary
print("Sorted dictionary is :")
for w in sorted(my_dict, key = my_dict.get,
                reverse = True):
    print(w, my_dict[w])
```

**Output**

```py
Sorted dictionary is :
white #FFFFFF
red #FF0000
green #008000
black #000000
```