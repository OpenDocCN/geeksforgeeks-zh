# C 小测验–111 |问题 1

> 原文:[https://www.geeksforgeeks.org/c-c-quiz-111-question-1/](https://www.geeksforgeeks.org/c-c-quiz-111-question-1/)

为以下程序片段选择最佳语句:

```cpp
#include <stdio.h>

int main()
{
 int var;  /*Suppose address of var is 2000 */

 void *ptr = &var;
 *ptr = 5;
 printf("var=%d and *ptr=%d",var,*ptr);

 return 0;
}
```

**(A)** 将打印“var=5 和* ptr = 2000”
**(B)**将打印“var=5 和* ptr = 5”
**(C)**将打印“var=5 和*ptr=XYZ”其中 XYZ 是一些随机地址
**(D)** 编译错误

**答案:** **(D)** 需要注意的是，void 指针的解引用是不允许的，因为 void 是一个不完整的数据类型。赋值为 5 的正确方法是首先类型化 void 指针，然后使用它。所以应该用 **(int *)ptr* 来代替 **ptr* 。正确答案是 d.

[本题小考](https://www.geeksforgeeks.org/c-quiz-111-gq/)