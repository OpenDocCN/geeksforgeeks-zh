# C |字符串|问题 10

> 原文:[https://www.geeksforgeeks.org/c-string-question-10/](https://www.geeksforgeeks.org/c-string-question-10/)

```cpp
#include <stdio.h>

void my_toUpper(char* str, int index)
{
    *(str + index) &= ~32;
}

int main()
{
    char* arr = "geeksquiz";
    my_toUpper(arr, 0);
    my_toUpper(arr, 5);
    printf("%s", arr);
    return 0;
}
```

**(A)** 极客 sQuiz
**(B)** 极客 squiz
**(C)** 编译器相关

**答案:****(C)**

**说明:**字符串 **arr** 的内存分配在数据段的只读/写区域。选择取决于编译器。在较新版本的编译器中，内存分配在数据区的只读部分。所以对字符串的任何修改都是不可能的。
在像 Turbo-C 这样的老版本编译器中，修改是可能的。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)