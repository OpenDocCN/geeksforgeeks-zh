# Python 中的无限迭代器

> 原文: [https://www.geeksforgeeks.org/infinite-iterators-in-python/](https://www.geeksforgeeks.org/infinite-iterators-in-python/)

[Python 中的迭代器](https://www.geeksforgeeks.org/iterators-in-python/)是可以与 "`for in` 循环"一起使用的任何 Python 类型。Python 列表、元组、字典和集合都是内置迭代器的例子。但是迭代器对象不必用尽，有时它可以是无限的。这种迭代器被称为 `无限迭代器`。

Python 提供了三种类型的无限迭代器：

## 1. `count(start, step)`

此迭代器从 "start" 数字开始打印并无限打印。如果指定了步长，则会跳过数字，否则默认步长为 1。请参阅下面的示例，了解其与 `for in` 循环的用法。

**示例:**

```py
# Python program to demonstrate
# infinite iterators

import itertools

# for in loop
for i in itertools.count(5, 5):
    if i == 35:
        break
    else:
        print(i, end =" ")
```

**输出:**

```py
5 10 15 20 25 30
```

## 2. `cycle(iterable)`

此迭代器按顺序打印传递容器中的所有值。当所有元素都以循环方式打印完毕后，它会重新从开头开始打印。

**示例#1:**

```py
# Python program to demonstrate
# infinite iterators

import itertools

count = 0

# for in loop
for i in itertools.cycle('AB'):
    if count > 7:
        break
    else:
        print(i, end = " ")
        count += 1
```

**输出:**

```py
A B A B A B A B
```

**示例#2:** 使用 `next()` 函数。

```py
# Python program to demonstrate
# infinite iterators

import itertools

l = ['Geeks', 'for', 'Geeks']

# defining iterator
iterators = itertools.cycle(l)

# for in loop
for i in range(6):

    # Using next function
    print(next(iterators), end = " ")
```

**输出:**

```py
Geeks for Geeks Geeks for Geeks
```

## 3. `repeat(val, num)`

此迭代器无限次重复打印传递的值。如果指定了可选关键字 `num`，则它会重复打印 `num` 次。

**示例:**

```py
# Python code to demonstrate the working of
# repeat()

# importing "itertools" for iterator operations
import itertools

# using repeat() to repeatedly print number
print ("Printing the numbers repeatedly : ")
print (list(itertools.repeat(25, 4)))
```

**输出:**

```py
Printing the numbers repeatedly :
[25, 25, 25, 25]
```