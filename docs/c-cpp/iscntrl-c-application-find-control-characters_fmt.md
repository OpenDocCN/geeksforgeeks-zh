# C++ 中的 `iscntrl()` 及其在查找控制字符中的应用

> 原文：[https://www.geeksforgeeks.org/iscntrl-c-application-find-control-characters/](https://www.geeksforgeeks.org/iscntrl-c-application-find-control-characters/)

在 C++ 中，`iscntrl()` 是用于字符串和字符处理的预定义函数。`cstring` 是字符串函数所需的头文件，`cctype` 是字符函数所需的头文件。控制字符是不可打印的字符，即它不占据显示器上的打印位置。

此函数用于检查参数是否包含任何控制字符。C++ 中有许多类型的控制字符，例如：
*   水平制表符 – `'\t'`
*   换行 – `'\n'`
*   退格 – `'\b'`
*   回车 – `'\r'`
*   换页 – `'\f'`
*   转义

## 语法

```cpp
int iscntrl ( int c );
```

## 应用程序

### 1. 给定一个字符串，我们需要找出字符串中控制字符的数量。

#### 算法
1.  逐个字符遍历给定的字符串直到其长度，检查该字符是否是控制字符。
2.  如果它是一个控制字符，将计数器加 1，否则遍历到下一个字符。
3.  打印计数器的值。

示例：

```cpp
Input : string='My name \n is \n Ayush'
Output :2

Input :string= 'This is written above \n This is written below'
Output :1
```

```cpp
// CPP program to count control characters in a string
#include <iostream>
#include <cstring>
#include <cctype>
using namespace std;

// function to calculate control characters
void space(string& str)
{
    int count = 0;
    int length = str.length();
    for (int i = 0; i < length; i++) {
        int c = str[i];
        if (iscntrl(c))
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

输出：

```cpp

```

### 2. 给定一个字符串，我们需要打印字符串直到找到一个控制字符。

#### 算法
1.  逐个字符遍历给定的字符串，并使用 `putchar()` 将字符写入标准输出。
2.  当在字符串中找到控制字符时，跳出循环。
3.  从标准输出打印最终的字符串。

示例：

```cpp
Input : string='My name is \n Ayush'
Output :My name is

Input :string= 'This is written above \n This is written below'
Output :This is written above
```

```cpp
// CPP program to print a string until a control character
#include <iostream>
#include <cstring>
#include <cctype>
#include<cstdio>
using namespace std;

// function to print string until a control character
int space(string& str)
{
     int i=0;
  while (!iscntrl(str[i]))
  {
    putchar (str[i]);
    i++ ;
  }
  return 0;
}

// Driver Code
int main()
{
    string str = "My name is \n Ayush";
    space(str);
    return 0;
}
```

输出：

```cpp
My name is
```

本文由 **Ayush Saxena** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。