# C |数组|问题 14

> 原文:[https://www.geeksforgeeks.org/c-arrays-question-14-2/](https://www.geeksforgeeks.org/c-arrays-question-14-2/)

```cpp
#include <stdio.h>
int main()
{
    char p;
    char buf[10] = {1, 2, 3, 4, 5, 6, 9, 8};
    p = (buf + 1)[5];
    printf("%d\n", p);
    return 0;
}
```

**(A)**5
**(B)**6
**(C)**9
**(D)**以上

**均无答案:****(C)**

**说明:**

[本题竞猜](http://quiz.geeksforgeeks.org/c-languag-2/arrays-pointers/)