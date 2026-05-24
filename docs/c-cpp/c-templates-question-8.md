# C++ |模板|问题 8

> 原文:[https://www.geeksforgeeks.org/c-templates-question-8/](https://www.geeksforgeeks.org/c-templates-question-8/)

输出？

```cpp
#include <iostream>
using namespace std;

template <int i>
void fun()
{
   i = 20;
   cout << i;
}

int main()
{
   fun<10>();
   return 0;
}
```

**(A)**10
**(B)**20
**(C)**编译器错误

**答案:****(C)**

**解释:**编译器错误在第“i = 20”行

非类型参数必须是常量，因此不能修改。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)