# Python – 获取字符串的最后 N 个字符

> 原文：[https://www.geeksforgeeks.org/python-get-last-n-characters-of-a-string/](https://www.geeksforgeeks.org/python-get-last-n-characters-of-a-string/)

给定一个字符串和一个整数 `N`，任务是编写一个 Python 程序来打印字符串的最后 `N` 个字符。

**示例：**

> **输入：** `Geeks For Geeks!`；`N = 4`
> **输出：** `ks!`
> **说明：** 给定的字符串是 `Geeks For Geeks!`，最后 4 个字符是 `ks!`。
>
> **输入：** `PYTHON`；`N = 1`
> **输出：** `N`
> **说明：** 给定的字符串是 `PYTHON`，最后一个字符是 `N`。

**方法 1：** 使用[循环](https://www.geeksforgeeks.org/loops-in-python/)获取给定字符串的最后 `N` 个字符。

## Python 3

```py
# get input
Str = "Geeks For Geeks!"
N = 4

# print the string
print(Str)

# iterate loop
while(N > 0):

# print character
    print(Str[-N], end='')

# decrement the value of N
    N = N-1
```

**输出：**

```py
Geeks For Geeks!
eks!
```

**方法 2：** 使用[列表切片](https://www.geeksforgeeks.org/python-list-slicing/)打印给定字符串的最后 `n` 个字符。

## Python

```py
# get input
Str = "Geeks For Geeks!"
N = 4

# print the string
print(Str)

# get length of string
length = len(Str)

# create a new string of last N characters
Str2 = Str[length - N:]

# print Last N characters
print(Str2)
```

**输出：**

```py
Geeks For Geeks!
eks!
```