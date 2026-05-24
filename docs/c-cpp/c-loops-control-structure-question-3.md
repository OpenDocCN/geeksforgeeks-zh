# C |循环&控制结构|问题 3

> 原文:[https://www . geesforgeks . org/c-loops-control-structure-question-3/](https://www.geeksforgeeks.org/c-loops-control-structure-question-3/)

下面程序的输出是什么？

```cpp
#include <stdio.h>
int main()
{
    int i = 0;
    switch (i)
    {
        case '0': printf("Geeks");
                break;
        case '1': printf("Quiz");
                break;
        default: printf("GeeksQuiz");
    }
    return 0;
} 
```

**(A)** 极客
**(B)** 小测验
**(C)** 极客 sQuiz
**(D)** 编译时错误

**答案:****(C)**

**解释:**乍一看，程序的输出好像是**极客**。但是，这些案例被标记为字符，这些字符被转换为 ascii 值 48(表示 0)和 49(表示 1)。这些案例都没有标记值 0。因此，控制转到默认块并打印**极客 sQuiz** 。