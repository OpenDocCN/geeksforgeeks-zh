# C |输入输出|问题 13

> 原文:[https://www . geesforgeks . org/c-输入输出-问题-1/](https://www.geeksforgeeks.org/c-input-and-output-question-1/)

预测后续程序的输出？

```cpp
#include "stdio.h"
int main()
{
    char arr[100];
    printf("%d", scanf("%s", arr));
    /* Suppose that input value given
        for above scanf is "GeeksQuiz" */
    return 1;
}
```

**(A)**9
**(B)**1
**(C)**10
**(D)**100

**回答:** **(B)**
**说明:**在 C 中，scanf 返回其已成功读取的输入数量。参见[https://www.geeksforgeeks.org/archives/674](https://www.geeksforgeeks.org/archives/674)
[本题小测验](https://www.geeksforgeeks.org/c-language-2-gq/input-and-output-gq/)

感谢您阅读《邮报》！