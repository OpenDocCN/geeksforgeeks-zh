# C/c++

中的 strxfrm()

> 原文:[https://www.geeksforgeeks.org/strxfrm-in-ccpp/](https://www.geeksforgeeks.org/strxfrm-in-ccpp/)

c/c++ 库 **strxfrm()** 将源字符串的字符转换为当前区域设置，并将其放置在目标字符串中。
使用在**场所定义的 LC_COLLATE 类别。h** 。strxfrm()函数执行转换的方式是，两个字符串上的 strcmp 结果与两个原始字符串上的 strcoll 结果相同。
**语法:**

```cpp
size_t strxfrm(char *str1, const char *str2, size_t num);
parameters:
str1 :is the string which receives 
num characters of transformed string. 
str2 : is the string which is to be transformed
num  :is the maximum number of characters
which to be copied into str1.
```

**示例:**

```cpp
Input : 'geeksforgeeks'
Output : 13

```

```cpp
// C program to demonstrate
// strxfrm()
#include <stdio.h>
#include <string.h>
int main()
{
    char src[10], dest[10];
    int len;
    strcpy(src, "geeksforgeeks");
    len = strxfrm(dest, src, 10);
    printf("Length of string %s is: %d", dest, len);

    return (0);
}
```

输出:

```cpp
Length of string geeksforgeeks is: 13

```

**例 2 :**

```cpp
Input : 'hello geeksforgeeks'
Output : 20 // in this example it count space also 

```

```cpp
// C program to demonstrate
// strxfrm()
#include <stdio.h>
#include <string.h>
int main()
{
    char src[20], dest[200];
    int len;
    strcpy(src, " hello geeksforgeeks");
    len = strxfrm(dest, src, 20);
    printf("Length of string %s is: %d", dest, len);

    return (0);
}
```

输出:

```cpp
Length of string  hello geeksforgeeks is: 20

```

**例 3 :**

```cpp
// C program to demonstrate
// strxfrm()
#include <iostream>
#include <string.h>
using namespace std;
int main()
{
    char str2[30] = "Hello geeksforgeeks";
    char str1[30];
    cout << strxfrm(str1, str2, 4) << endl;
    cout << str1 << endl;
    cout << str2 << endl;
    return 0;
}
```

输出:

```cpp
19
Hell
Hello geeksforgeeks

```

本文由**希瓦尼·巴盖尔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。