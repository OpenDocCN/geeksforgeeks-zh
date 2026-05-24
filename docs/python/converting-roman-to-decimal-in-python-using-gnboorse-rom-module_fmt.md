# 使用 gnboorse-rom 模块将 Python 中的罗马转换为十进制

> 原文: [https://www.geeksforgeeks.org/converting-roman-to-decimal-in-python-using-gnboorse-rom-module/](https://www.geeksforgeeks.org/converting-roman-to-decimal-in-python-using-gnboorse-rom-module/)

`gnboorse-rom` 模块是一个 Python 库，帮助你把罗马数字转换成十进制数字，十进制数字转换成罗马数字。它可以转换罗马数字和十进制中高达 3999 的值。

**注:** 以下是一些独特的罗马符号及其对应的十进制值的列表。

```py
SYMBOL        VALUE
I      ->       1
IV     ->       4
V      ->       5
IX     ->       9
X      ->       10
XL     ->       40
L      ->       50
XC     ->       90
C      ->       100
CD     ->       400
D      ->       500
CM     ->       900 
M      ->       1000
```

罗马数字中的数字是由这些符号按降序排列而成的字符串（例如，先写 M，后写 D，等等）。然而，在一些特定的情况下，为了避免四个字符连续重复（如 IIII 或 XXXX），减法符号经常被使用如下：

*   I 放在 V 或 X 前面表示少了一个，所以四是 IV（少了一个 5），九是 IX（少了一个 10）。
*   放在 L 或 C 前面的 X 表示少了十个，所以四十是 XL（10 比 50 少），90 是 XC（十比一百少）。
*   放在 D 或 M 前面的 C 表示少了一百，所以四百是 CD（一百少于五百），九百是 CM（一百少于一千）。

## 安装库

这个模块没有内置 Python。你需要从外部安装它。要安装此模块，请在终端中键入以下命令。

```py
pip install gnboorse-rom
```

## 主要功能

*   **1-rom_generate**: 它将我们的十进制数字转换为罗马数字，并返回一个罗马数字字符串作为输出。
    **示例:**

```py
    # Importing rom_generate function
    # From gnboorse's rom Library
    from rom import rom_generate

    a = rom_generate(1)
    print(a)

    a = rom_generate(5)
    print(a)

    a = rom_generate(15)
    print(a)

    a = rom_generate(255)
    print(a)

    a = rom_generate(512)
    print(a)

    a = rom_generate(786)
    print(a)

    a = rom_generate(1444)
    print(a)

    a = rom_generate(2000)
    print(a)

    a = rom_generate(3999)
    print(a)
    type(a)
```

**输出:**

```py
I
V
XV
CCLV
DXII
DCCLXXXVI
MCDXLIV
MM
MMMCMXCIX
str
```

*   **2-rom_parse**: 它将我们的罗马数字转换为十进制数字，并返回一个十进制整数作为输出。
    **示例:**

```py
    # Importing rom_parse function
    # From gnboorse's rom Library
    from rom import rom_parse

    a = rom_parse('I')
    print(a)

    a = rom_parse('XV')
    print(a)

    a = rom_parse('L')
    print(a)

    a = rom_parse('CCLV')
    print(a)

    a = rom_parse('CD')
    print(a)

    a = rom_parse('MXII')
    print(a)

    a = rom_parse('DDD')
    print(a)

    a = rom_parse('MMD')
    print(a)

    a = rom_parse('MMMCMXCIX')
    print(a)
    type(a)
```

**输出:**

```py
int
```

**注:** 要了解逻辑背后的代码，可以参考 [GeeksforGeeks](https://www.geeksforgeeks.org/converting-decimal-number-lying-between-1-to-3999-to-roman-numerals/)。