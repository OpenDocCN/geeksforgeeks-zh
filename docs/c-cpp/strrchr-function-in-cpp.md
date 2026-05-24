# C/c++

中的 strrchr()函数

> 原文:[https://www.geeksforgeeks.org/strrchr-function-in-cpp/](https://www.geeksforgeeks.org/strrchr-function-in-cpp/)

**str chr()函数**
在 C++ 中，str chr()是一个用于字符串处理的预定义函数。cstring 是字符串函数所需的头文件。
该函数返回字符串中最后一个字符的指针。
我们要查找的最后一个字符作为第二个参数传递给函数，我们要查找的字符串作为第一个参数传递给函数。
**语法**

```cpp
char *strrchr(const char *str, int c)
```

这里，str 是字符串，c 是要定位的字符。它作为其 int 提升传递，但在内部转换回 char。
**应用程序**
在 C++ 中给定一个字符串，我们需要找到一个字符的最后一次出现，比如说‘a’。
示例:

```cpp
Input : string = 'This is a string'
Output :9

Input :string = 'My name is Ayush'
Output :12
```

**算法**
1。在 strchr()函数中传递给定的字符串，并提及您需要指向的字符。
2。该函数返回值，打印该值。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate working strchr()
#include <iostream>
#include <cstring>
using namespace std;

int main()
{
  char str[] = "This is a string";
  char * ch = strrchr(str,'a');
  cout << ch - str + 1;
  return 0;
}
```

输出:

```cpp
9
```

**C 例:**

## C

```cpp
// C code to demonstrate the working of
// strrchr()

#include <stdio.h>
#include <string.h>

// Driver function
int main()
{

    // initializing variables
    char st[] = "GeeksforGeeks";
    char ch = 'e';
    char* val;

    // Use of strrchr()
    // returns "ks"
    val = strrchr(st, ch);

    printf("String after last %c is :  %s \n", ch, val);

    char ch2 = 'm';

    // Use of strrchr()
    // returns null
    // test for null
    val = strrchr(st, ch2);

    printf("String after last %c is :  %s ", ch2, val);

    return (0);
}
```

输出:

```cpp
String after last e is :  eks 
String after last m is :  (null)
```

**实际应用:**由于是在某个特定字符最后一次出现后返回整个字符串，所以可以用来**提取字符串的后缀**。例如，当我们知道第一个数字时，就能知道一个面额的所有前导零。下面演示了这个例子。

## C

```cpp
// C code to demonstrate the application of
// strrchr()

#include <stdio.h>
#include <string.h>

// Driver function
int main()
{

    // initializing the denomination
    char denom[] = "Rs 10000000";

    // Printing original string
    printf("The original string is : %s", denom);

    // initializing the initial number
    char first = '1';
    char* entire;

    // Use of strrchr()
    // returns entire number
    entire = strrchr(denom, first);

    printf("\nThe denomination value is : %s ", entire);

    return (0);
}
```

输出:

```cpp
The original string is : Rs 10000000
The denomination value is : 10000000
```

本文由**阿尤什·萨塞纳****瓦伊什纳维·特里帕蒂**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。