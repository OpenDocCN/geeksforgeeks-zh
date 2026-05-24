# c++ 中的 regex _ error

> 原文:[https://www.geeksforgeeks.org/regex_error-in-c/](https://www.geeksforgeeks.org/regex_error-in-c/)

**正则表达式错误**出现在标题“正则表达式”和**类正则表达式错误中；**。它帮助我们了解程序执行过程中抛出的错误，它定义了正则表达式库中异常对象的类型，还描述了 basic_regex 对象的构造或使用中的一个错误。构造一个用于保存值错误的对象起着重要的作用，这是从 **std:: exception** 继承的

下面列出了十三种错误类型:

| 【旗帜】 | 【 Errors 】 |
| --- | --- |
| Error _ collate | The element names of these expressions have invalid collation. |
| Error _ ctype | This expression has invalid character class name. |
| Error _ stack | If there is not enough memory to determine whether a regular expression can match a given character sequence. |
| Error _ space | This happens in order to convert to finite state machine when there is insufficient memory. |
| Error _ bad repeat | This contains a repetition specifier (*? +{) is not preceded by a valid regular expression. |
| Error _ complexity | When invalid character range is included, the complexity of matching attempt for regular expression exceeds the preset level |
| Error _ range |  |
| Error _ badbrake | The expression contains an invalid range between braces {and}. |
| Error _ brake | The expression contains mismatched braces {and}. |
| Error _ Paren | The expression contains mismatched brackets (and). |
| Error _ Brack | The expression contains mismatched brackets ([and]). |
| Error _ backref | This expression excludes invalid back reference. |
| Error _ escape | This expression does not allow any invalid escape characters or trailing escape. |
| Error _ escape | This expression does not allow any invalid escape characters or trailing escape. |
|  |  |

下面是一个演示正则表达式错误的简单程序。

**程序 1:**

```cpp
// Program to demonstrate the error
int main()
{
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
    }
    return 0;
}
```

**输出:**

```cpp
regex_error caught: Unexpected character in bracket expression.
        The code gives an error_brack
```

**节目 2:**

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