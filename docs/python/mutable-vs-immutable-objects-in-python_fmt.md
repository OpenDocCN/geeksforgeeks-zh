# Python 中可变与不可变对象

> 原文：[https://www.geeksforgeeks.org/mutable-vs-immutable-objects-in-python/](https://www.geeksforgeeks.org/mutable-vs-immutable-objects-in-python/)

Python 中的每个变量都保存一个对象的实例。Python 中有两种类型的对象，即**可变的**和**不可变的对象**。每当一个对象被实例化时，它被分配一个唯一的对象 id。对象的类型是在运行时定义的，以后不能更改。但是，如果它是一个可变对象，它的状态可以改变。

总而言之，可变对象可以改变它们的状态或内容，而不可变对象不能改变它们的状态或内容。

*   **不可变对象：** 这些是内置类型，如 `int`、`float`、`bool`、`string`、`unicode`、`tuple`。简单来说，不可变对象在创建后不能被改变。

```py
# Python code to test that
# tuples are immutable

tuple1 = (0, 1, 2, 3)
tuple1[0] = 4
print(tuple1)
```

错误：

```py
Traceback (most recent call last):
  File "e0eaddff843a8695575daec34506f126.py", line 3, in
    tuple1[0]=4
TypeError: 'tuple' object does not support item assignment
```

```py
# Python code to test that
# strings are immutable

message = "Welcome to GeeksforGeeks"
message[0] = 'p'
print(message)
```

错误：

```py
Traceback (most recent call last):
  File "/home/ff856d3c5411909530c4d328eeca165b.py", line 3, in
    message[0] = 'p'
TypeError: 'str' object does not support item assignment
```

*   **可变对象：** 这些是 `list`、`dict`、`set` 类型。自定义类通常是可变的。

```py
# Python code to test that
# lists are mutable
color = ["red", "blue", "green"]
print(color)

color[0] = "pink"
color[-1] = "orange"
print(color)
```

输出：

```py
['red', 'blue', 'green']
['pink', 'blue', 'orange']
```

## 结论

1.  Python 中可变和不可变对象的处理方式不同。不可变对象的访问速度更快，更改的成本也更高，因为这涉及到副本的创建。而易变的对象很容易改变。
2.  当需要改变对象的大小或内容时，建议使用可变对象。
3.  **例外情况：** 然而，不可变性也有例外。我们知道 Python 中的元组是不可变的。但元组由一系列名称组成，这些名称与对象的绑定是不可更改的。
    考虑一个元组：

```py
tup = ([3, 4, 5], 'myname')
```

元组由一个字符串和一个列表组成。字符串是不可变的，所以我们不能改变它的值。但是列表的内容可以改变。**元组本身不是可变的，但是包含可变的项。**

根据经验，一般来说，类似原语的类型可能是不可变的，而定制的类似容器的类型大多是可变的。