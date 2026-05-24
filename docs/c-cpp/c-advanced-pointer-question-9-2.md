# C |高级指针|问题 9

> 原文:[https://www . geesforgeks . org/c-advanced-pointer-question-9-2/](https://www.geeksforgeeks.org/c-advanced-pointer-question-9-2/)

```cpp
#include <stdio.h>
#include <stdlib.h>

int main(void)
{
    int i;
    int *ptr = (int *) malloc(5 * sizeof(int));

    for (i=0; i<5; i++)
        *(ptr + i) = i;

    printf("%d ", *ptr++);
    printf("%d ", (*ptr)++);
    printf("%d ", *ptr);
    printf("%d ", *++ ptr);
    printf("%d ", ++*ptr);
}
```

**(A)** 编译错误
**(B)**0 1 2 2 3
**(C)**0 1 2 3 4
**(D)**1 2 3 4 5

**回答:****(B)**

**解释:**处理此类问题需要记住的重要事项有

**1)** 前缀++ 和*运算符具有相同的优先级和从右向左的结合性。

**2)** Postfix ++ 的优先级高于上面提到的两个运算符，结合性从左到右。

我们可以应用以上两个规则来猜测所有

*ptr++ 被视为*(ptr++)

* +++ ptr 被视为*(+++ ptr)

++*ptr 被视为++(*ptr)

[本题小测验](https://www.geeksforgeeks.org/c-language-2-gq/advanced-pointer-c-gq/)