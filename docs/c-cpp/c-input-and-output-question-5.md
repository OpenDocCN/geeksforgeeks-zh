# C |输入输出|问题 5

> 原文:[https://www . geesforgeks . org/c-输入输出-问题-5/](https://www.geeksforgeeks.org/c-input-and-output-question-5/)

预测以下程序的输出:

```cpp
#include <stdio.h>

int main()
{
    printf("%c ", 5["GeeksQuiz"]);
    return 0;
}
```

**(A)** 编译时错误
**(B)** 运行时错误
**(C)**Q
**(D)**s

**答案:****(C)**

**解释:**程序的症结在于表达式: **5[【极客 squiz】**
这个将字符串的基址加 5 会增加指针(假设指针最初指向字符串的开始( **G** ))指向 **Q** 。应用**的值-**运算符给出指针所指位置的字符，即该题的问答