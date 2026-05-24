# C++ |构造函数|问题 9

> 原文:[https://www.geeksforgeeks.org/c-constructors-question-9/](https://www.geeksforgeeks.org/c-constructors-question-9/)

预测后续程序的输出。

```cpp
#include<iostream>
#include<stdlib.h>
using namespace std;

class Test
{
public:
   Test()
   { cout << "Constructor called"; }
};

int main()
{
    Test *t = (Test *) malloc(sizeof(Test));
    return 0;
}
```

**(A)** 构造函数调用
**(B)** 空
**(C)** 编译器错误
**(D)** 运行时错误

**答案:****(B)**

**解释:**与 new 不同，malloc()不调用构造函数(参见[本](https://www.geeksforgeeks.org/malloc-vs-new/))

如果用 new 替换 malloc()，则调用构造函数，参见[本](http://ideone.com/l7APkK)。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)