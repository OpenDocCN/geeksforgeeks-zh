# 在 C/C++ 中复制字符串的不同方式

> 原文:[https://www . geeksforgeeks . org/differential-to-copy-a-string-in-c/](https://www.geeksforgeeks.org/different-ways-to-copy-a-string-in-c-c/)

### <u>使用内置功能</u>

### strcpy（）：

使用内置函数 [strcpy()](https://www.geeksforgeeks.org/strcpy-in-c-cpp/) 从 [**string.h**](https://www.geeksforgeeks.org/commonly-used-string-functions-in-c-c-with-examples/) 头文件中复制一个字符串到另一个字符串。strcpy()接受指向目标数组和源数组的指针作为参数，并在复制后返回指向目标字符串的指针。使用%s，我们可以打印字符串(%s 打印从基地址到空字符的字符串)。

下面是使用上述方法的实现:

## C

```cpp
// C program to copy the string using
// strcpy function

#include <stdio.h>
#include <stdlib.h>
#include <string.h>

// Function to copy the string
char* copyString(char s[])
{
    char* s2;
    s2 = (char*)malloc(20);

    strcpy(s2, s);
    return (char*)s2;
}

// Driver Code
int main()
{
    char s1[20] = "GeeksforGeeks";
    char* s2;

    // Function Call
    s2 = copyString(s1);
    printf("%s", s2);
    return 0;
}
```

**输出:**

```cpp
GeeksforGeeks
```