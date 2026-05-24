# C

中的 strspn()函数

> 原文:[https://www.geeksforgeeks.org/strspn-function-c/](https://www.geeksforgeeks.org/strspn-function-c/)

**strspn()** 函数返回由 *str1* 指向的字符串的初始子字符串的长度，该长度仅由包含在由 *str2* 指向的字符串中的那些字符组成。

语法:

```cpp
size_t strspn(const char *str1, const char *str2)
str1 : string to be scanned.
str2 : string containing the 
characters to match.
Return Value : This function
returns the number of characters
in the initial segment of str1 
which consist only of characters 
from str2.
```

```cpp

// C program to illustrate strspn() function
#include <stdio.h>
#include <string.h>

int main () {
   int len = strspn("geeks for geeks","geek");
   printf("Length of initial segment matching : %d\n", len );    
   return(0);
}
```

输出:

```cpp
Length of initial segment matching 4
```

```cpp

// C program to illustrate strspn() function
#include <stdio.h>
#include <string.h>

int main () {
   int len = strspn("i am","xyz");
   printf("Length of initial segment matching : %d\n", len );
   return(0);
}
```

输出:

```cpp
Length of initial segment matching 0
```

本文由**Shivani ghishial**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。