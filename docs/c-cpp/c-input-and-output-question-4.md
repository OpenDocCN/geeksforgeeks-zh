# C |输入输出|问题 4

> 原文:[https://www . geesforgeks . org/c-输入输出-问题-4/](https://www.geeksforgeeks.org/c-input-and-output-question-4/)

```cpp
#include <stdio.h>
// Assume base address of "GeeksQuiz" to be 1000
int main()
{
   printf(5 + "GeeksQuiz");
   return 0;
}
```

**(A)**GeeksQuiz
**(B)**小测验
**(C)**1005
**(D)**编译时错误

**答案:****(B)**

**解释:**

**printf** 是在 *stdio.h* 头文件下定义的库函数。编译器通过表达式 ***5 +【极客 squiz】***将 5 添加到字符串的基址。然后字符串“小测验”作为参数传递给标准库函数。