# Python compile()函数

> 原文: [https://www.geeksforgeeks.org/python-compile-function/](https://www.geeksforgeeks.org/python-compile-function/)

`Python compile()`函数以源代码为输入，返回一个准备执行的代码对象，这个代码对象以后可以被`exec()`函数执行。

> **语法:** `compile(source, filename, mode, flags=0, dont_inherit=False, optimize=-1)`
>
> **参数:**
>
> *   `source` – 可以是普通字符串、字节字符串或 AST 对象
> *   `filename` - 这是读取代码的文件。如果不是从文件中读取的，您可以自己命名。
> *   `mode` – 模式可以是执行模式、评估模式或单一模式。
>     *   `eval` – 如果源是单个表达式。
>     *   `exec` – 它可以取一个包含 Python 语句、类和函数等的代码块。
>     *   `single` – 如果由单个交互语句组成，则使用该语句
> *   `flags`(可选)和 `dont_inherit`(可选) – 默认值=0。它注意哪些未来的语句会影响源代码的编译。
> *   `optimize`(可选) – 告知编译器的优化级别。默认值-1。

## Python compile()函数示例

### 示例 1: Python 中的简单 compile() 示例

这里 `filename` 是 `mulstring`，`exec` 模式允许使用 `exec()` 方法，`compile` 方法将字符串转换为 Python 代码对象。

```py
# Python code to demonstrate working of compile().

# Creating sample sourcecode to multiply two variables
# x and y.
srcCode = 'x = 10\ny = 20\nmul = x * y\nprint("mul =", mul)'

# Converting above source code to an executable
execCode = compile(srcCode, 'mulstring', 'exec')

# Running the executable code.
exec(execCode)
```

**输出:**

```py
mul = 200
```

### 示例 2: 另一个演示 compile() 的例子

```py
# Another Python code to demonstrate working of compile().
x = 50

# Note eval is used for single statement
a = compile('x', 'test', 'single')
print(type(a))
exec(a)
```

**输出:**

```py
<class 'code'>
```

### 示例 3: Python 从文件编译函数

在这个例子中，我们将使用一些字符串显示方法获取 `main.py` 文件，然后我们读取文件内容并编译它来编码对象并执行它。

**main.py:**

```py
String = "Welcome to Geeksforgeeks"
print(String)
```

**Code:** 这里我们将文件内容作为字符串读取，然后编译成一个 Code 对象。

```py
# reading code from a file
f = open('main.py', 'r')
temp = f.read()
f.close()

code = compile(temp, 'main.py', 'exec')
exec(code)
```

**输出:**

```py
Welcome to Geeksforgeeks
```

### 示例 4: 使用 eval() 编译()

这里，当源是单个表达式时，使用 `eval`。

```py
# Another Python code to demonstrate
# working of compile() with eval.
x = 50

# Note eval is used for statement
a = compile('x == 50', '', 'eval')
print(eval(a))
```

**输出:**

```py
True
```

## 应用

1.  如果 Python 代码是字符串形式或者是 AST 对象，并且您想要将其更改为代码对象，则可以使用 `compile()` 方法。
2.  `compile()` 方法返回的代码对象稍后可以使用 `exec()` 和 `eval()` 等方法调用，这些方法将执行动态生成的 Python 代码。