# Python 中的 `codeop.compile_command`

> 原文: [https://www.geeksforgeeks.org/codeop-compile_command-in-python/](https://www.geeksforgeeks.org/codeop-compile_command-in-python/)

借助 `codeop.compile_command()` 方法，我们可以通过编译单行或多行代码来检查语法错误。

> **语法:** `codeop.compile_command(code)`
> **返回:** 返回对象或编译错误(如果有)。

## 示例#1

在这个示例中，我们可以看到，通过使用 `codeop.compile_command()` 方法，我们能够编译多行代码。

```py
# import codeop
from codeop import compile_command

code = 'a = 5 b = 9; print(a + b)'
# Using codeop.compile_command() method
compile_command(code)
```

**输出:**

```
  File "<input>", line 1
    a = 5 b = 9; print(a + b)
             ^
SyntaxError: invalid syntax
```

## 示例#2

```py
# import codeop
from codeop import compile_command

code = '-a = 5'
# Using codeop.compile_command() method
compile_command(code)
```

**输出:**

```
SyntaxError: cannot assign to operator
```