# 如何在 Python 中检查一个字符串是否是有效的关键字？

> 原文: [https://www.geeksforgeeks.org/check-string-valid-keyword-python/](https://www.geeksforgeeks.org/check-string-valid-keyword-python/)

## 定义关键词

在编程中，一个关键词是一个“保留词”，其语言向解释者传达了特殊的含义。它可以是命令或参数。关键字不能在程序片段中用作变量名。

## Python 中的关键词

Python 语言也保留了一些传达特殊含义的关键词。这些知识是学习这门语言的必要部分。下面是 Python 注册的关键词列表。

`False`, `None`, `True`, `and`, `as`, `assert`, `break`, `class`, `continue`, `def`, `del`, `elif`, `else`, `except`, `finally`, `for`, `from`, `global`, `if`, `import`, `in`, `is`, `lambda`, `nonlocal`, `not`, `or`, `pass`, `raise`, `return`, `try`, `while`, `with`, `yield`

## 如何检查一个字符串是否是关键字？

Python 在其语言中定义了一个内置模块 `keyword`，它处理与关键字相关的某些操作。函数 `iskeyword()` 检查字符串是否是关键字。如果字符串是关键字，则返回 `True`，否则返回 `False`。

### 代码示例

```py
# importing "keyword" for keyword operations
import keyword

# initializing strings for testing while putting them in an array
keys = ["for", "while", "tanisha", "break", "sky",
        "elif", "assert", "pulkit", "lambda", "else", "sakshar"]

for i in range(len(keys)):
    # checking which are keywords
    if keyword.iskeyword(keys[i]):
        print(keys[i] + " is a python keyword")
    else:
        print(keys[i] + " is not a python keyword")
```

### 输出

```
for is a python keyword
while is a python keyword
tanisha is not a python keyword
break is a python keyword
sky is not a python keyword
elif is a python keyword
assert is a python keyword
pulkit is not a python keyword
lambda is a python keyword
else is a python keyword
sakshar is not a python keyword
```

## 如何打印所有关键词的列表

有时，在分配变量名时，记住所有的关键词可能是一项困难的任务。因此在 `keyword` 模块中提供了函数 `kwlist()`，该模块打印所有 33 个 Python 关键字。

### 代码示例

```py
# importing "keyword" for keyword operations
import keyword

# printing all keywords at once using "kwlist()"
print("The list of keywords is : ")
print(keyword.kwlist)
```

### 输出

```
The list of keywords is : 
['False', 'None', 'True', 'and', 'as', 'assert', 'break', 'class', 'continue', 'def', 'del', 'elif', 'else', 'except', 'finally', 'for', 'from', 'global', 'if', 'import', 'in', 'is', 'lambda', 'nonlocal', 'not', 'or', 'pass', 'raise', 'return', 'try', 'while', 'with', 'yield']
```

## 下一篇文章

*   [Python 中的关键词|集合 1](https://www.geeksforgeeks.org/keywords-python-set-1/)
*   [Python 中的关键词|第二集](https://www.geeksforgeeks.org/keywords-python-set-2/)

本文由 [**曼吉特·辛格(S.Nandini)**](https://www.facebook.com/manjeet.04.singh) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [write.geeksforgeeks.org](https://write.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。