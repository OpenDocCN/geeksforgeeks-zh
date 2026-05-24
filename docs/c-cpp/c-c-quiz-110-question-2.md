# C 小测验–110 |问题 2

> 原文:[https://www.geeksforgeeks.org/c-c-quiz-110-question-2/](https://www.geeksforgeeks.org/c-c-quiz-110-question-2/)

以下程序无法编译，因为宏名和左括号之间有空格。

```cpp
#include "stdio.h"

#define MYINC   (  a  )  (  ( a )  +  1 )

int main()
{

 printf("GeeksQuiz!");

 return 0;
}
```

**(A)** 真
**(B)** 假

**答案:** **(B)**

**解释:**请注意#define 是一个预处理器指令，即在实际编译发生之前处理。在上面的程序片段中，MYINC 没有在程序中的任何地方使用。因此，即使 MYINC 没有执行预期的行为，即它不会增加，但 MYINC 是一个有效的宏。如果我们在程序中的任何地方使用 MYINC，它将被替换为“(a ) ( ( a ) + 1)”。因此，上述程序将编译和运行没有任何问题。

[本题小考](https://www.geeksforgeeks.org/c-quiz-110-gq/)