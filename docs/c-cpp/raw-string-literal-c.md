# c++ 中的原始字符串文字

> 原文:[https://www.geeksforgeeks.org/raw-string-literal-c/](https://www.geeksforgeeks.org/raw-string-literal-c/)

原始字符串是不处理 C++ 的转义字符如 **\n** 、 **\t** 或**\**的字符串。因此，这是在 C++ 11 中引入的，它是一个原始字符串，以 **R 开头，以“”结尾。**

**原始字符串文字的语法:**

```cpp
R "delimiter( raw_characters )delimiter"
```

这里，分隔符是可选的，它可以是除反斜杠(/)、空格( )和括号( () )之外的字符。

这些原始字符串文字通过像原始字符序列一样精确地写入其内容来允许一系列字符。以下是普通字符串文字和原始字符串文字的示例:

**普通字符串**

```cpp
"\\\\n"
```

**原始字符串文字**

```cpp
R"(\\n)"
```

我们来看一个在 C++ 中查看原始字符串文字的例子:

T3】CPPT5

```cpp
// C++ program to demonstrate working of raw string literal
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    // A Normal string
    string string1 = "Geeks.\nFor.\nGeeks.\n";

    // A Raw string
    string string2 = R"(Geeks.\nFor.\nGeeks.\n)";

    cout << string1 << endl;

    cout << string2 << endl;

    return 0;
}
```

T6T8**输出**T1

本文由 **MAZHAR IMAM KHAN** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](http://www.write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。