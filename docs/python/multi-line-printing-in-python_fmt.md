# Python 多行打印

> 原文：[`https://www.geeksforgeeks.org/multi-line-printing-in-python/`](https://www.geeksforgeeks.org/multi-line-printing-in-python/)

我们已经看到了`print function`[的基本用法，上一篇文章](https://www.geeksforgeeks.org/python-output-using-print-function/)。现在，让我们看看如何使用`print function`进行多行打印。这可以使用多行字符串，即三个单引号`''' Geeksforgeks '''`轻松完成。

让我们看不同的例子来看相同的演示。

## 示例 #1:

```py
# basic example for multi-line printing
print(
'''
=======================================
|                                     |
|                                     |
|          GeeksforGeeks              |
|                                     |
|                                     |
=======================================
'''
    )
```

**Output:**

```py
=======================================
|                                     |
|                                     |
|          GeeksforGeeks              |
|                                     |
|                                     |
=======================================
```

## 例 2:

```py
# basic example2 for multi-line printing
print(
  '''list.head        second              third 
         |                |                  | 
         |                |                  | 
    +----+------+     +----+------+     +----+------+ 
    | 1  | None |     | 2  | None |     |  3 | None | 
    +----+------+     +----+------+     +----+------+ 
    '''
    )
```

**Output:**

```py
list.head        second              third 
         |                |                  | 
         |                |                  | 
    +----+------+     +----+------+     +----+------+ 
    | 1  | None |     | 2  | None |     |  3 | None | 
    +----+------+     +----+------+     +----+------+
```