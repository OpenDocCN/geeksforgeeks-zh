# C 小测验–109 |问题 4

> 原文:[https://www.geeksforgeeks.org/c-c-quiz-109-question-4/](https://www.geeksforgeeks.org/c-c-quiz-109-question-4/)

找出以下程序的正确语句。

```cpp
#include "stdio.h"

int * gPtr;

int main()
{
 int * lPtr = NULL;

 if(gPtr == lPtr)
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

**(A)** 它会一直打印相等。
**(B)** 它会一直印不平等。
**(C)** 由于 gPtr 在程序中没有初始化，它有时会打印相等，有时会打印不相等。

**回答:****(A)**

**说明:**需要注意的是，gPtr(是指向 int 的全局指针)等全局变量被初始化为零。这就是为什么 gPtr(它是一个全局指针，隐式初始化)和 lPtr(它是一个本地指针，显式初始化)会有相同的值，即正确答案是 a.

[这个问题的测验](https://www.geeksforgeeks.org/c-quiz-109-gq/)