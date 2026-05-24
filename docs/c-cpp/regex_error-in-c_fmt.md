# c++ 中的 regex_error

> 原文:[https://www.geeksforgeeks.org/regex_error-in-c/](https://www.geeksforgeeks.org/regex_error-in-c/)

**正则表达式错误**出现在标题“正则表达式”和**类正则表达式错误中；**。它帮助我们了解程序执行过程中抛出的错误，它定义了正则表达式库中异常对象的类型，还描述了 `basic_regex` 对象的构造或使用中的一个错误。构造一个用于保存值错误的对象起着重要的作用，这是从 `std::exception` 继承的。

## 下面列出了十三种错误类型:

| 【旗帜】 | 【 Errors 】 |
| --- | --- |
| `error_collate` | The element names of these expressions have invalid collation. |
| `error_ctype` | This expression has invalid character class name. |
| `error_stack` | If there is not enough memory to determine whether a regular expression can match a given character sequence. |
| `error_space` | This happens in order to convert to finite state machine when there is insufficient memory. |
| `error_badrepeat` | This contains a repetition specifier (`*?+{`) is not preceded by a valid regular expression. |
| `error_complexity` | When invalid character range is included, the complexity of matching attempt for regular expression exceeds the preset level |
| `error_range` |  |
| `error_badbraces` | The expression contains an invalid range between braces `{` and `}`. |
| `error_braces` | The expression contains mismatched braces `{` and `}`. |
| `error_paren` | The expression contains mismatched brackets `(` and `)`. |
| `error_brack` | The expression contains mismatched brackets `[` and `]`. |
| `error_backref` | This expression excludes invalid back reference. |
| `error_escape` | This expression does not allow any invalid escape characters or trailing escape. |
| `error_escape` | This expression does not allow any invalid escape characters or trailing escape. |
|  |  |

## 下面是一个演示正则表达式错误的简单程序。

### 程序 1:

```cpp
// Program to demonstrate the error
#include <iostream>
#include <regex>

int main()
{
    try {
        std::regex re("[1-9][0");
    }

    catch (const std::regex_error& err) {
        std::cout << "There was a regex_error caughted: " 
        << err.what() << '\n';
        if (err.code() == std::regex_constants::error_brack) {
            std::cout << "The code gives an error_brack\n";
        }
    }
    return 0;
}
```

### 输出:

```cpp
regex_error caught: Unexpected character in bracket expression.
        The code gives an error_brack
```

### 节目 2:

```cpp
// Program to demonstrate no error
#include <iostream>
#include <regex>

int main()
{
    try {
        std::regex re("[A-Z][bcd] ");
    }

    catch (const std::regex_error& er) {
        std::cout << "regex_error caught: "
        << er.what() << '\n';
        if (er.code() == std::regex_constants::error_brack) {
            std::cout << "The code was this is the error error_brack\n";
        }
    }
}
```

**注意:**没有输出，因为没有错误。