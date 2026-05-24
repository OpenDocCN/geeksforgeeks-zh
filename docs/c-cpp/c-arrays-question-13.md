# C |数组|问题 13

> 原文:[https://www.geeksforgeeks.org/c-arrays-question-13/](https://www.geeksforgeeks.org/c-arrays-question-13/)

```cpp
#include<stdio.h>
int main()
{
    int a[10][20][30] = {0};
    a[5][2][1] = 2;
    return 0;
}
```

以下哪一项将打印上述代码的值 2？
**(A)** printf("%d "，*((A+5)+2)+1))；
**(B)**printf(" % d " ,* * *((a+5)+2)+1)；
**(C)** printf("%d "，*(*(*(a+5)+2)+1))；
**(D)** 这些都不是

**答案:****(C)**

**解释:**

[本题竞猜](http://quiz.geeksforgeeks.org/c-languag-2/arrays-pointers/)