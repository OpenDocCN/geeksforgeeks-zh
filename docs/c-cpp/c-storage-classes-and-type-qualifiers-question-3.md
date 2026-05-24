# C |存储类和类型限定符|问题 3

> 原文:[https://www . geesforgeks . org/c-storage-class-and-type-qualifier-question-3/](https://www.geeksforgeeks.org/c-storage-classes-and-type-qualifiers-question-3/)

```cpp
#include <stdio.h>
int main()
{
    static int i=5;
    if (--i){
        printf("%d ",i);
        main();
    }
}
```

**(A)**4 3 2 1
**(B)**1 2 3 4
**(C)**4 4 4 4
**(D)**0 0 0

**答案:****(A)**

**解释:**由于 I 是静态变量，所以在对 main()的所有调用中共享。所以每次函数调用都会减少 1。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)