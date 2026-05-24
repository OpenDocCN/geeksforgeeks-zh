# C++ |这个指针|问题 5

> 原文:[https://www.geeksforgeeks.org/c-this-pointer-question-5/](https://www.geeksforgeeks.org/c-this-pointer-question-5/)

预测下面 C++ 程序的输出？

```cpp
#include<iostream>
using namespace std;

class Test
{
private:
  int x;
public:
  Test() {x = 0;}
  void destroy()  { delete this; }
  void print() { cout << "x = " << x; }
};

int main()
{
  Test obj;
  obj.destroy();
  obj.print();
  return 0;
}
```

**(A)** x = 0
**(B)** 未定义行为
**(C)** 编译器错误

**答案:****(B)**

**说明:**删除操作符只对使用操作符 new 分配的对象有效(见[本帖](https://www.geeksforgeeks.org/g-fact-30/))。如果对象是使用 new 创建的，那么我们可以删除它，否则行为是未定义的。

更多例子参见 C++ 中[“删除这个”](https://www.geeksforgeeks.org/delete-this-in-c/)。

[本题小考](https://www.geeksforgeeks.org/c-plus-plus-gq/this-pointer-gq/)