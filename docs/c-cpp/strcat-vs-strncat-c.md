# c++ 中的 strcat()vs strn cat()

> 原文:[https://www.geeksforgeeks.org/strcat-vs-strncat-c/](https://www.geeksforgeeks.org/strcat-vs-strncat-c/)

**strcat()**

函数的作用是:在目标字符串的末尾添加一个源字符串的副本。strcat()函数接受两个参数:
1) dest
2) src
它将在目标字符串中追加源字符串的副本。**dest 末尾的终止字符被 src 的第一个字符替换。**
**返回值:**strcat()函数返回 dest，即指向目标字符串的指针。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate
// strcat
#include <cstring>
#include <iostream>
using namespace std;
int main()
{
    char dest[50] = "This is an";
    char src[50] = " example";

    strcat(dest, src);
    cout << dest ;
    return 0;
}
```

**输出:**

```cpp
This is an example
```

[**【strncat()**](https://www.geeksforgeeks.org/strncat-function-in-c-cpp/)

C++ 中的 strncat()函数将一个字符串中给定数量的字符追加到另一个字符串的末尾。strncat()函数将接受这三个参数:
1)目的地
2) Src
3)计数
这将在目的地字符串的末尾追加给定数量的字符。**目的字符串末尾的终止字符将被 src 字符串的第一个字符**替换。
**返回值:**strncat()函数返回 dest，即指向目的字符串的指针。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate
// strncat
#include <cstring>
#include <iostream>

using namespace std;

int main()
{
    char dest[25] = "This is an example";
    char src[50] = " to show working of strncat() this is not added";

strncat(dest, src, 29);
    cout << dest ;
    return 0;

}
```

**输出:**

```cpp
This is an example to show working of strncat()
```

【strncat()和 strcat()有什么不同？

许多程序员建议，与 strcat()相比，strcat()是安全的，因为 str cat()不会检查复制数据的大小，并且会一直复制到空终止符，这可能会导致缓冲区溢出，而 str cat()会检查复制数据的大小，并且只会复制“n”个字节。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C,C++ program demonstrate difference between
// strncat() and strcat()
#include <stdio.h>
#include <string.h>

int main()
{

   // Take any two strings
   char src[50] = "forgeeks";
   char dest1[50] = "geeks";
   char dest2[50] = "geeks";

   printf("Before strcat() function execution, ");
   printf("destination string : %s\n", dest1);

   // Appends the entire string of src to dest1
   strcat(dest1, src);

   // Prints the string
   printf("After strcat() function execution, ");
   printf("destination string : %s\n", dest1);

   printf("Before strncat() function execution, ");
   printf("destination string : %s\n", dest2);

   // Appends 3 characters from src to dest2
   strncat(dest2, src, 3);

   // Prints the string
   printf("After strncat() function execution, ");
   printf("destination string : %s\n", dest2);

   return 0;
}
```

**输出:**

```cpp
Before strcat() function execution, destination string : geeks
After strcat() function execution, destination string : geeksforgeeks
Before strncat() function execution, destination string : geeks
After strncat() function execution, destination string : geeksfor
```

本文由**普拉纳夫**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。