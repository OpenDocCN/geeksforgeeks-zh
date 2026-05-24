# C |输入输出|问题 6

> 原文:[https://www . geesforgeks . org/c-输入输出-问题-6/](https://www.geeksforgeeks.org/c-input-and-output-question-6/)

预测以下程序的输出:

```cpp
#include <stdio.h>
int main()
{
    printf("%c ", "GeeksQuiz"[5]);
    return 0;
}
```

**(A)** 编译时错误
**(B)** 运行时错误
**(C)**Q
**(D)**s

**答案:****(C)**

**解释:**程序的症结在于表达式:**【GeeksQuiz】【5】**。
这个表达式被编译器分解为:*(“GeeksQuiz”+5)。将字符串的基址加 5 会使指针(假设指针最初指向字符串的开始( **G** )指向 q。应用**值-of** 运算符会在指针指向的位置给出字符，即 q