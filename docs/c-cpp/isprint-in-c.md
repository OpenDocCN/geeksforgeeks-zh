# 是 C++ 中的 print()

> 原文:[https://www.geeksforgeeks.org/isprint-in-c/](https://www.geeksforgeeks.org/isprint-in-c/)

在 C++ 中，isprint()是用于字符串和字符处理的预定义函数。cstring 是字符串函数所需的头文件，cctype 是字符函数所需的头文件。

此函数用于检查参数是否包含任何可打印字符。C++ 中有许多类型的可打印字符，例如:

*   数字(0123456789)
*   大写字母(ABCDEFGHIJKLMNOPQRSTUVWXYZ)
*   小写字母(abcdefghijklmnopqrstuvwxyz)
*   标点符号(！"#$%&'()*+,-./:;？@[\]^_`{ | }~ )
*   空间( )

**语法:**

```cpp
int isprint ( int c ); 
c : character to be checked.
Returns a non-zero value(true) if c is a printable 
character else, zero (false).

```

在 C++ 中给定一个字符串，我们需要计算字符串中可打印字符的数量。
**算法**

1.  逐个字符遍历给定的字符串直到其长度，检查字符是否为可打印字符。
2.  如果是可打印字符，将计数器加 1，否则遍历到下一个字符。
3.  打印计数器的值。

示例:

```cpp
Input : string = 'My name \n is \n Ayush'
Output : 18

Input :string = 'I live in \n Dehradun'
Output : 19

```

```cpp
// CPP program to count printable characters in a string
#include <iostream>
#include <cstring>
#include <cctype>
using namespace std;

// function to calculate printable characters
void space(string& str)
{
    int count = 0;
    int length = str.length();
    for (int i = 0; i < length; i++) {
        int c = str[i];
        if (isprint(c))
            count++ ;
    }
    cout << count;
}

// Driver Code
int main()
{
    string str = "My name \n is \n Ayush";
    space(str);
    return 0;
} 
```

输出:

```cpp
18

```

本文由 **Ayush Saxena** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。