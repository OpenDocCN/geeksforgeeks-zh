# C++ |继承|问题 4

> 原文:[https://www.geeksforgeeks.org/c-inheritance-question-4/](https://www.geeksforgeeks.org/c-inheritance-question-4/)

```cpp
#include<iostream>

using namespace std;
class P {
public:
   void print()  { cout <<" Inside P"; }
};

class Q : public P {
public:
   void print() { cout <<" Inside Q"; }
};

class R: public Q { };

int main(void)
{
  R r; 
  r.print();
  return 0;
}
```

**(A)** 内 P
**(B)** 内 Q
**(C)** 编译器错误:对 print()的模糊调用

**答案:****(B)**

**解释:**print 函数在 r 类中不存在，所以在继承层次中查找。print()在 P 和 Q 两个类中都存在，应该调用哪一个？其思想是，如果存在多级继承，则函数在继承层次中线性向上搜索，直到找到匹配的函数。

[本题小测验](https://www.geeksforgeeks.org/quiz-corner-gq/)