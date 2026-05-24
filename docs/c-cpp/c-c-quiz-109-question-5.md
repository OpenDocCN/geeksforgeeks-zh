# C 小测验–109 |问题 5

> 原文:[https://www.geeksforgeeks.org/c-c-quiz-109-question-5/](https://www.geeksforgeeks.org/c-c-quiz-109-question-5/)

找出以下程序的正确语句。

```cpp
#include "stdio.h"

int * arrPtr[5];

int main()
{
 if(*(arrPtr+2) == *(arrPtr+4))
 {
   printf("Equal!");
 }
 else
 {
  printf("Not Equal");
 }
 return 0;
}
```

**(甲)**编译错误
**(乙)**它会一直打印相等。
**(C)** 总会打印不相等。
**(D)** 由于 arrPtr 的元素在程序中没有初始化，它会打印“相等”或“不相等”。

**回答:****(B)**

**解释:**这里 arrPtr 是指向 int 的指针的全局数组。需要注意的是，像 arrPtr 这样的全局变量被初始化为零。这就是为什么 arrPtr 的所有 is 元素都被隐式初始化为 ZERO，即正确答案是 b .这个问题的

[测试](https://www.geeksforgeeks.org/c-quiz-109-gq/)