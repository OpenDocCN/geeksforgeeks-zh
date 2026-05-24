# Python 中如何清屏？

> 原文：[https://www.geeksforgeeks.org/clear-screen-python/](https://www.geeksforgeeks.org/clear-screen-python/)

大多数时候，在使用 `python interactive shell/terminal`（而不是控制台）时，我们最终会得到一个混乱的输出，并且出于某种原因想要清除屏幕。
在交互式外壳/终端中，我们可以简单地使用

```py
ctrl+l
```

但是，如果我们想在运行 `python` 脚本时清除屏幕，该怎么办。
可惜没有内置关键字或函数/方法来清屏。所以，我们可以使用 `ANSI` 转义序列，但这些是不可移植的，可能不会产生所需的输出。

```py
print(chr(27)+'[2j')
print('\033c')
print('\x1bc')
```

所以，我们在脚本中要做的是：

1.  从 `os` 导入 `system`。
2.  定义函数。
3.  使用 `'clear'`（在 `Linux` 中）和 `'cls'`（在 `Windows` 中）作为参数进行 `system` 调用。
4.  将返回值存储在 `_` 或任何你想要的变量中（使用 `_` 是因为 `python shell` 总是将其最终输出存储在 `_` 中）。
5.  调用我们定义的函数。

```py
# import only system from os
from os import system, name

# import sleep to show output for some time period
from time import sleep

# define our clear function
def clear():

# for windows
    if name == 'nt':
        _ = system('cls')

# for mac and linux(here, os.name is 'posix')
    else:
        _ = system('clear')

# print out some text
print('hello geeks\n'*10)

# sleep for 2 seconds after printing output
sleep(2)

# now call function we defined above
clear()
```

注意：您也可以只 `import os` 而不是 `from os import system`，但是您必须将 `system('clear')` 更改为 `os.system('clear')`。

实现这一点的另一种方法是使用 `subprocess` 模块。

```py
# import call method from subprocess module
from subprocess import call

# import sleep to show output for some time period
from time import sleep

# define clear function
def clear():
    # check and make call for specific operating system
    _ = call('clear' if os.name == 'posix' else 'cls')

print('hello geeks\n'*10)

# sleep for 2 seconds after printing output
sleep(2)

# now call function we defined above
clear()
```