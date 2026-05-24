# Python 中 yield 和 return 的差异

> 原文: [https://www.geeksforgeeks.org/difference-between-yield-and-return-in-python/](https://www.geeksforgeeks.org/difference-between-yield-and-return-in-python/)

## Python Yield

`yield` 一般用于将一个常规 Python 函数转换成生成器。生成器是 Python 中的一个特殊函数，它向调用方返回一个生成器对象。由于它存储局部变量状态，因此控制了内存分配的开销。

**示例:**

```py
# Python3 code to demonstrate yield keyword

# Use of yield
def printresult(String):
    for i in String:
        if i == "e":
            yield i

# initializing string
String = "GeeksforGeeks"
ans = 0
print("The number of 'e' in word is : ", end="")
String = String.strip()

for j in printresult(String):
    ans = ans + 1

print(ans)
```

**输出:**

```py
The number of 'e' in word is : 4
```

## Python Return

`return` 一般用于结束执行并将结果“返回”给调用者语句。它可以返回所有类型的值，并且当没有带有语句 `return` 的表达式时，它返回 `None`。

**示例:**

```py
# A Python program to show return statement
class Test:
    def __init__(self):
        self.str = "GeeksForGeeks"
        self.x = "Shubham Singh"

# This function returns an object of Test
def fun():
    return Test()

# Driver code to test above method
t = fun()
print(t.str)
print(t.x)
```

**输出:**

```py
GeeksForGeeks
Shubham Singh
```

## Python yield 和 return 之间的差异

| 序号 | yield | return |
| :--- | :--- | :--- |
| 1 | `yield` 通常用于将常规 Python 函数转换为生成器。 | `return` 通常用于结束执行，并将结果“返回”给调用者语句。 |
| 2 | 它取代了函数的返回，在不破坏局部变量的情况下暂停函数的执行。 | 它从一个函数中退出，并将一个值返回给它的调用方。 |
| 3 | 当生成器向调用者返回中间结果时使用它。 | 当函数准备发送值时使用。 |
| 4 | 在下一次函数调用中执行 `yield` 语句后编写的代码。 | 而在 `return` 语句之后编写的代码不会执行。 |
| 5 | 它可以运行多次。 | 它只运行一次。 |
| 6 | `yield` 语句函数从函数暂停的最后一个状态开始执行。 | 每个函数调用从一开始就运行函数。 |