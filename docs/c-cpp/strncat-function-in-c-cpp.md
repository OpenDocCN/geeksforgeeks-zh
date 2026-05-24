# C/c++

中的 strncat()函数

> 原文:[https://www.geeksforgeeks.org/strncat-function-in-c-cpp/](https://www.geeksforgeeks.org/strncat-function-in-c-cpp/)

在 C/C++ 中，strncat()是用于字符串处理的预定义函数。 **string.h** 是字符串函数所需的头文件。
该函数将 src 指向的字符串中不超过 **n** 个字符追加到 dest 指向的字符串末尾，并加上一个终止的空字符。字符串的初始字符(src)会覆盖字符串末尾的空字符(dest)。因此，字符串(dest)的长度变为 strlen(dest)+n。但是，如果字符串(src)的长度小于 **n** ，则仅复制直到终止空字符的内容，并且字符串(dest)的长度变为 strlen(src) + strlen(dest)。
如果出现以下情况，则行为未定义

*   琴弦重叠了。
*   dest 数组不够大，无法追加 src 的内容。

**语法:**

```cpp
char *strncat(char *dest, const char *src, size_t n)
```

**参数:**该方法接受以下参数:

*   **dest** :我们要追加的字符串。
*   **src** :要追加“n”个字符的字符串。
*   **n** :表示要追加的最大字符数。size_t 是无符号整数类型。

**返回值:**strncat()函数将返回指向字符串(dest)的指针。

**应用**
给定 C++ 中的两个字符串 src 和 dest，我们需要在 src 和 dest 之间追加‘n’个字符，假设 n=5。

**示例:**

```cpp
Input:  src = "world"
        dest = "Hello "
Output: "Hello world"

Input:  src = "efghijkl"
        dest = "abcd"
Output: "abcdefghi"
```

**程序:**

## C++

```cpp
// C,C++ program demonstrate functionality of strncat()
#include <cstring>
#include <iostream>
using namespace std;

int main()
{

   // Take any two strings
   char src[50] = "efghijkl";
   char dest[50]= "abcd";

   // Appends 5 character from src to dest
   strncat(dest, src, 5);

   // Prints the string
   cout <<"Source string : "<< src << endl;
   cout <<"Destination string : "<< dest;

   return 0;
}

// This code is contributed by shivanisinghss2110
```

## C

```cpp
// C,C++ program demonstrate functionality of strncat()
#include <stdio.h>
#include <string.h>

int main()
{

   // Take any two strings
   char src[50] = "efghijkl";
   char dest[50]= "abcd";

   // Appends 5 character from src to dest
   strncat(dest, src, 5);

   // Prints the string
   printf("Source string : %s\n", src);
   printf("Destination string : %s", dest);

   return 0;
}
```

**输出:**

```cpp
Source string : efghijkl
Destination string : abcdefghi
```

【strncat()和 strcat()有什么不同？
很多程序员都建议，与 strcat()相比，strcat()是安全的，因为 strcat()不会检查复制数据的大小，并且会一直复制到一个空终止符，这可能会导致缓冲区溢出，而 strcat()会检查复制数据的大小，并且只会复制“n”个字节。

## C++

```cpp
// C,C++ program demonstrate difference between
// strncat() and strcat()
#include <cstring>
#include <iostream>
using namespace std;

int main()
{

   // Take any two strings
   char src[50] = "forgeeks";
   char dest1[50] = "geeks";
   char dest2[50] = "geeks";

   cout << "Before strcat() function execution, ";
   cout << "destination string : "<< dest1 << endl;

   // Appends the entire string of src to dest1
   strcat(dest1, src);

   // Prints the string
   cout << "After strcat() function execution, ";
   cout << "destination string : "<< dest1 << endl;

   cout << "Before strncat() function execution, ";
   cout << "destination string : "<< dest2 << endl;

   // Appends 3 characters from src to dest2
   strncat(dest2, src, 3);

   // Prints the string
   cout << "After strncat() function execution, ";
   cout << "destination string : "<< dest2 << endl;

   return 0;
}

// this code is contributed by shivanisinghss2110
```

## C

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

本文由**阿卡什·古普塔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。