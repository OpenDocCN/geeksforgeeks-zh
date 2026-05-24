# C | C 测验–113 |问题 1

> 原文:[https://www . geesforgeks . org/intentity-c-quick-113-question-1-2/](https://www.geeksforgeeks.org/aptitude-c-quiz-113-question-1-2/)

假设数字以二进制补码形式存储，则输出以下程序。

```cpp
#include<stdio.h>
int main()
{
   printf("%c\n", ~('C' * -1));
   return 0;
}
```

索姆亚供稿。l . R
**(A)**B
**(B)**A
**(C)**编译器错误
**(D)**C

**答案:****(A)**

**解释:**执行时没有任何错误或警告消息，上述代码的输出为
“B”
被处理
的 ASCII 值“C”是 67，它乘以-1 作为
67 *(1)=-67
步骤 2:
67 的二进制表示是 10111101
1011101 的按位求反变成(01000010 ) 2 = (66) 10
步骤 3:
66 是“B”
的 ASCII 值所以