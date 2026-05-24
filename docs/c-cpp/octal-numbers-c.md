# c 中的八进制数

> 原文:[https://www.geeksforgeeks.org/octal-numbers-c/](https://www.geeksforgeeks.org/octal-numbers-c/)

C 语言中有一些不太为人所知的事实与八进制数有关。让我们先看看下面的示例代码。

示例:

```cpp
// program to show octal number interpretation
#include <stdio.h>

int main()
{
    int x = 012;
    printf("%d", x);
    return 0;
}
```

**输出:**

```cpp
10

```

令人惊讶的是，输出不是 12。发生这种情况是因为前面有 0 的整数被解释为八进制数。十进制值 12 的八进制数是 10。但是如果 x 等于 092，那么编译器会显示一个错误，因为 92 不是一个有效的八进制数。

**八进制[转义序列](https://www.geeksforgeeks.org/escape-sequences-c/)**
在 C 语言中八进制转义序列由\后跟三个八进制数字表示。请注意，也允许一个或两个八进制数字。八进制序列要么在\后的三个八进制数字后结束，要么在\后的数字不是八进制数字时结束。

示例:

```cpp
// program to show octal escape sequence
#include <stdio.h>
int main()
{
    char str[] = "31\01267";
    printf("%s", str);
    return 0;
}
```

**输出:**

```cpp
31
67

```

如果我们看输出，那么在 31 之后，一个新行字符被打印，然后 67 被打印。这是因为\012 被解释为\n 或新的行字符。实际上，\012 代表\n 或换行符的八进制转义序列。十进制中八进制值 12 是 10，在 ASCII 中它代表换行符。

```cpp
// program to show octal escape sequence
#include <stdio.h>
int main()
{
    char str[] = "31\12367";
    printf("%s", str);
    printf("\n");
    char str2[] = "11\77967";
    printf("%s", str2);
    return 0;
}
```

**输出:**

```cpp
31S67
11?967

```

在 str \123 中解释为八进制转义序列，八进制 123 的值是 83，在我的机器中与之对应的字符是“S”，因为我的机器使用 ASCII。如果使用的字符集不是 ASCII，则可能会有所不同。
在 str2 中\77 被解释为八进制转义序列，而不是\779。所以，77 的值在十进制中是 63，在 ASCII 中是“？”。

本文由 **Ashish Sharma** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。