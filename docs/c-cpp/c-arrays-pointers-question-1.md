# C |数组|问题 1

> 原文:[https://www.geeksforgeeks.org/c-arrays-pointers-question-1/](https://www.geeksforgeeks.org/c-arrays-pointers-question-1/)

预测以下程序的输出:

```cpp
#include <stdio.h>

int main()
{
    int arr[5];

    // Assume that base address of arr is 2000 and size of integer
        // is 32 bit
    arr++ ;
    printf("%u", arr);

    return 0;
}
```

**(A)**2002
**(B)**2004
**(C)**2020
**(D)**左值必选

**答案:****(D)**

**说明:**C 中的数组名是通过常量指针实现的。不可能对常量类型应用增量和减量。