# Python 中的 PyInputPlus 模块

> 原文: [https://www.geeksforgeeks.org/pyinputplus-module-in-python/](https://www.geeksforgeeks.org/pyinputplus-module-in-python/)

`PyInputPlus` 是一个 Python 模块，用于获取具有附加验证功能的输入。`PyInputPlus` 将继续向用户询问文本，直到他们输入有效的输入。

## 安装

通过 `pip` 命令安装模块:

```py
pip install PyInputPlus
```

以下是用于进行各种类型输入的函数:

*   `inputNum()`: 接受数值。它需要额外的参数 "minimum"、"maximum"、"greater than" 和 "less than" 作为边界。返回 `int` 或 `float`。
*   `inputStr()`: 接受字符串值。它提供诸如 "blockRegexes"、"Timeout" 和 "Limit" 等功能。
*   `inputInt()`: 接受整数值。这同样需要额外的参数 "minimum"、"maximum"、"greater than" 和 "less than" 作为边界。返回一个整数。
*   `inputFloat()`: 接受浮点数值。同样需要额外的 Minimum、Maximum、Greater than 和 Less than 参数。返回一个浮点数。
*   `inputBool()`: 接受布尔值。输入可以是 "true"/"false" 和 "t"/"f" 的任何不区分大小写的形式。返回一个布尔值。
*   `inputChoice()`: 获取一个字符串列表并接受其中一个作为输入。
*   `inputMenu()`: 类似于 `inputChoice()`，但选项显示为菜单中的项目。菜单项可以使用 "letters" 和 "numbers" 参数用字母或数字标记。
*   `inputDate()`: 接受 `strftime` 格式的日期。我们需要将此格式传递给 "formats" 参数。返回一个 `datetime.date` 对象。
*   `inputTime()`: 接受 `strftime` 格式的时间。返回一个 `datetime.time` 对象。
*   `inputDateTime()`: 接受 `strftime` 格式的日期和时间。返回一个 `datetime.datetime` 对象。
*   `inputYesNo()`: 接受不区分大小写的 Yes/No 或 Y/N。返回 Yes 或 No。

### 一些示例用法

#### 1. 字符串输入

`inputStr()` 函数用于获取字符串输入。我们可以设置 `prompt` 参数，在输入前定义一个提示。类似于内置函数 `input()` 的 `prompt` 参数。通过将 `blank` 参数设置为 `True`，我们可以允许空白值作为有效输入。通过将 `blockRegexes` 参数的值设置为我们想要使其无效的正则表达式模式，可以阻止某些输入（即这些值无效）。

```py
import pyinputplus as pyip

# string input with
# additional parameters
inp = pyip.inputStr(prompt="Enter a string... ",
                    blank=True, blockRegexes = 'aeiou')

print(inp)
```

**输出:**

```py
Enter a string... Hello
This response is invalid.
Enter a string... GFG
GFG
```

#### 2. 整数输入

`inputInt()` 函数用于进行整数输入。如果传递了任何非整数输入，函数将重试，直到给出有效输入、时间耗尽或超过最大尝试次数。`default` 参数用于在时间耗尽或尝试次数超过时设置默认值。`limit` 参数用于指定用户输入有效输入的最大尝试次数，之后返回 `default` 值（如果指定的话），否则将引发 `RetryLimitException`。

```py
import pyinputplus as pyip

# integer input with
# limited number of tries
inp = pyip.inputInt(prompt = "Enter an Integer... ",
                    default = 0, limit = 3)

print(inp)
```