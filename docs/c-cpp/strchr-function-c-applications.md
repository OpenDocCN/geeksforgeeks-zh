# c++ 中的 strchr()函数及其应用

> 原文:[https://www . geesforgeks . org/strchr-function-c-applications/](https://www.geeksforgeeks.org/strchr-function-c-applications/)

在 C++ 中，strchr()是一个预定义的函数，用于查找字符串中出现的字符。它存在于 cstring 头文件中。

**语法**

```cpp
// Returns pointer to the first occurrence
// of c in str[]
char *strchr(const char *str, int c) 
```

请注意，c 是作为其 int 提升传递的，但它在内部被视为 char。
**应用程序**
在 c++ 中给定一个字符串，我们需要找到一个字符的第一次出现，比如说‘a’。

**示例:**

```cpp
Input : str[] = 'This is a string'
Output : 9

Input : str[] = 'My name is Ayush'
Output : 5
```

**算法**
1。在 strchr()函数中传递给定的字符串，并提到您需要指向的字符。
2。该函数返回值，打印该值。

下面是上述算法的实现:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to find position of a character
// in a given string.
#include <iostream>
#include <cstring>
using namespace std;

int main()
{
    char str[] = "My name is Ayush";
    char* ch = strchr(str, 'a');
    cout << ch - str + 1;
    return 0;
}
```

**Output**

```cpp
5
```

**strchr()** 函数也可以用来检查字符串中是否存在字符。输入包含一个我们想要检查的字符，如果它存在于字符串中。
例如–让我们检查字符串中是否存在字符 A 和 z–“我的名字是阿尤什”

```cpp
Input : str[] = 'My name is Ayush', 
        ch1 = 'A', ch2 = 'z'
Output : A is present in the string
         z is not present in the string
```

**算法**
1。在 strchr()函数中传递给定的字符串，并将字符作为第二个参数，并检查返回的值是否不为空
2。如果函数返回空值，这意味着字符串不包含字符，因此，打印所需的语句。
3。否则，如果函数没有返回空值，这意味着字符串包含字符，所以，打印所需的语句。

下面是上述算法的实现:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate working of strchr()
#include <iostream>
#include <cstring>
using namespace std;
// Driver code
int main()
{
    char str[] = "My name is Ayush";
    char ch = 'A', ch2 = 'z';
    if (strchr(str, ch) != NULL)
        cout << ch << " "
             << "is present in string" << endl;
    else
        cout << ch << " "
             << "is not present in string" << endl;
    if (strchr(str, ch2) != NULL)
        cout << ch2 << " "
             << "is present in string" << endl;
    else
        cout << ch2 << " "
             << "is not present in string" << endl;
    return 0;
}
```

**Output:** 

```cpp
A is present in string
z is not present in string
```

**strchr()函数可用于查找 Linux 的绝对目录路径:**(由 [Ekta_nehwal](https://auth.geeksforgeeks.org/user/Ekta_nehwal/articles) 供稿)

**示例:**

```cpp
Input : /home/test/sample
Output : /home/test
```

**算法:**

1.  使用 strrchr 查找目录路径中最后一个“/”的位置。
2.  用空字符替换匹配项。

下面是上述算法的实现:

## C

```cpp
// C program to find directory path
#include <string.h>
#include<stdio.h>

int main()
{
   char string[]={"/home/test/sample"};
   int len;

    //position of last char
    char* pos;

    // save length of string
    len = strlen(string);

    // Find the last character with
    pos = strrchr(string,'/') ;
    printf("%s\n",string);

    // replace last occurrence of / with NULL character.
    *pos='\0';                 
    printf("%s\n",string);

    return 0;
}
```

**Output**

```cpp
/home/test/sample
```

本文由 **Ayush Saxena** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](http://www.write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。