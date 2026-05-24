# C++ |函数重载和默认参数|问题 2

> 原文:[https://www.geeksforgeeks.org/c-this-pointer-question-6/](https://www.geeksforgeeks.org/c-this-pointer-question-6/)

输出？

```cpp
#include<iostream>
using namespace std;

int fun(int x = 0, int y = 0, int z)
{  return (x + y + z); }

int main()
{
   cout << fun(10);
   return 0;
}
```

**(A)**10
**(B)**0
**(C)**20
**(D)**编译器错误

**答案:****(D)**

**解释:**所有默认参数必须是最右边的参数。以下程序运行良好，并产生 10 作为输出。

```cpp
#include <iostream>
using namespace std;

int fun(int x, int y = 0, int z = 0)
{  return (x + y + z); }

int main()
{
   cout << fun(10);
   return 0;
}

```

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)