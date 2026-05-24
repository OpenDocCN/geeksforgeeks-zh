# C/c++ 中的 strcpy

> 原文:[https://www.geeksforgeeks.org/strcpy-in-c-cpp/](https://www.geeksforgeeks.org/strcpy-in-c-cpp/)

strcpy()是 C/C++ 中的标准库函数，用于将一个字符串复制到另一个字符串。在 C 语言中，它存在于**字符串. h** 头文件中，在 C++ 中，它存在于**字符串**头文件中。

**语法:**

```cpp
char* strcpy(char* dest, const char* src);
```

**参数:**该方法接受以下参数:

*   **目的地**:指向要复制内容的目标数组的指针。
*   **src:** 将要复制的字符串。

**返回值:**将源字符串复制到目标字符串后，strcpy()函数返回一个指向目标字符串的指针。

下面的程序解释了这个库函数的不同用法:

## C++

```cpp
// C++ program to illustrate
// strcpy() function ic C/C++
#include <iostream>
using namespace std;
#include<string.h>

int main ()
{
    char str1[]="Hello Geeks!";
    char str2[] = "GeeksforGeeks";
    char str3[40];
    char str4[40];
    char str5[] = "GfG";

    strcpy(str2, str1);
    strcpy(str3, "Copy successful");
    strcpy(str4, str5);
    cout << "str1: " << str1 << "\nstr2: " << str2 <<"\nstr3: "<< str3 << "\nstr4: "<< str4;
    return 0;
}

// this code is contributed by shivanisinghss2110
```

## C

```cpp
// C program to illustrate
// strcpy() function ic C/C++
#include<stdio.h>
#include<string.h>

int main ()
{
    char str1[]="Hello Geeks!";
    char str2[] = "GeeksforGeeks";
    char str3[40];
    char str4[40];
    char str5[] = "GfG";

    strcpy(str2, str1);
    strcpy(str3, "Copy successful");
    strcpy(str4, str5);
    printf ("str1: %s\nstr2: %s\nstr3: %s\nstr4:
                  %s\n", str1, str2, str3, str4);
    return 0;
}
```

**输出:**

```cpp
str1: Hello Geeks!
str2: Hello Geeks!
str3: Copy successful
str4: GfG
```

**重要点**

*   该函数将整个字符串复制到目标字符串。它不会将源字符串追加到目标字符串中。换句话说，我们可以说它用源字符串的内容替换了目的字符串的内容。
*   它不影响源字符串。复制后，源字符串保持不变。
*   该函数只适用于 C 风格的字符串，不适用于 C++ 风格的字符串，即只适用于 **char str[]类型的字符串；**而不是**弦 S1；**使用 C++ 中可用的标准字符串数据类型创建，而不是 C

本文由 **Harsh Agarwal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。