# C |输入输出|第 11 题

> 原文:[https://www . geesforgeks . org/c-输入输出-问题-11/](https://www.geeksforgeeks.org/c-input-and-output-question-11/)

预测后续程序的输出？

```cpp
#include <stdio.h>
int main(void) 
{
   int x = printf("GeeksQuiz");
   printf("%d", x);
   return 0;
}
```

**(A)** 极客 sQuiz9
**(B)** 极客 sQuiz10
**(C)** 极客 squiz9
**(D)**极客 sQuiz1

**答案:****(A)**

**解释:**printf 函数返回屏幕上成功打印的字符数。字符串“极客 sQuiz”有 9 个字符，因此第一个 printf 打印极客 sQuiz 并返回 9。

[本题小考](http://quiz.geeksforgeeks.org/basics/)