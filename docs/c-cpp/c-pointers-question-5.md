# C |指针基础|第 17 题

> 原文:[https://www.geeksforgeeks.org/c-pointers-question-5/](https://www.geeksforgeeks.org/c-pointers-question-5/)

假设 float 取 4 个字节，预测下一个程序的输出。

```cpp
#include <stdio.h>

int main()
{
    float arr[5] = {12.5, 10.0, 13.5, 90.5, 0.5};
    float *ptr1 = &arr[0];
    float *ptr2 = ptr1 + 3;

    printf("%f ", *ptr2);
    printf("%d", ptr2 - ptr1);

   return 0;
}
```

**(甲)** 90.500000
3

**(B)**90.500000
12
**(C)**10.000000
12
T8】(D)0.500000
3

**回答:****(A)**

**说明:**当我们给指针加一个值 x 时同样的规则也适用于减法。请注意，只能在指针中添加或减去整数值。我们还可以减去或比较两个相同类型的指针。

[本题小考](https://www.geeksforgeeks.org/c-language-2-gq/pointers-gq/)