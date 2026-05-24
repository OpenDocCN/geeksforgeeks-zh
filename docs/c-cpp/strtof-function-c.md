# 在 C

中设置功能

> 原文:[https://www.geeksforgeeks.org/strtof-function-c/](https://www.geeksforgeeks.org/strtof-function-c/)

解析 C-string 字符串(假设)，将其内容解释为浮点数(根据当前区域设置)，并将其值作为浮点数返回。如果 endptr(结束指针)不是空指针，该函数还将 endptr 的值设置为指向数字后的第一个字符。

**语法:**

```cpp
strtof(const char* str, char **endptr)
Parameters:
str : String object with the representation of floating point number
endptr : Reference to an already allocated object of type char*, 
whose value is set by the function to the next character in str after the numerical value.
This parameter can also be a null pointer, in which case it is not used.
Return Value : On success, the function returns the
 converted floating-point number as a value of type float.
```

```cpp
// C code to convert string having
// floating point as its content
// using strtof function

#include <stdio.h>
#include <stdlib.h> // Header file containing strtof function

int main()
{
    // Character array to be parsed
    char array[] = "365.25 7.0";

    // Character end pointer
    char* pend;

    // f1 variable to store float value
    float f1 = strtof(array, &pend);

    // f2 variable to store float value
    float f2 = strtof(pend, NULL);

    // Printing parsed float values of f1 and f2
    printf("%.2f\n%.2f\n", f1, f2);

    // Performing operation on the values returned
    printf(" One year has %.2f weeks \n", f1 / f2);

    return 0;
}
```

输出:

```cpp
365.25
7.0
One year has 52.18 weeks
```

本文由 **Mohak Agrawal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。