# C |操作员|问题 8

> 原文:[https://www.geeksforgeeks.org/c-operators-question-8/](https://www.geeksforgeeks.org/c-operators-question-8/)

```cpp
#include <stdio.h>
int main()
{
    //Assume sizeof character is 1 byte and sizeof integer is 4 bytes
    printf("%d", sizeof(printf("GeeksQuiz")));
    return 0;
}
```

**(A)** 极客 squiz4
**(B)**4geeksquick
**(C)**极客 squiz9
**(D)**4
**(E)**编译时错误

**答案:****(D)**

**解释:**一个表达式不会被评估**极客 sQuiz** 不会打印。 **printf** 返回要打印的字符数，即 9，这是一个整数值。 **sizeof** 运算符返回 sizeof(int)。