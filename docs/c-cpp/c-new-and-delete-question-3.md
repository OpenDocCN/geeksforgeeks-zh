# C++ |新增和删除|问题 3

> 原文:[https://www.geeksforgeeks.org/c-new-and-delete-question-3/](https://www.geeksforgeeks.org/c-new-and-delete-question-3/)

预测产量？

```cpp
#include <iostream>
using namespace std;

class Test 
{
  int x;
  Test() { x = 5;}
};

int main()
{
   Test *t = new Test;
   cout << t->x;
}
```

**(A)** 编译器错误
**(B)** 5
**(C)** 垃圾值
**(D)**0

**答案:****(A)**

**说明:**存在编译器错误:Test::Test()为私有。

new 调用构造函数。在 Test 类中，构造函数是私有的(注意在 C++ 中默认访问是私有的)。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)