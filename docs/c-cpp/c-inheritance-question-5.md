# C++ |继承|问题 5

> 原文:[https://www.geeksforgeeks.org/c-inheritance-question-5/](https://www.geeksforgeeks.org/c-inheritance-question-5/)

输出？

```cpp
#include<iostream>
using namespace std;

class Base {
private:
     int i, j;
public:
    Base(int _i = 0, int _j = 0): i(_i), j(_j) { }
};
class Derived: public Base {
public:
     void show(){
        cout<<" i = "<<i<<"  j = "<<j;
     }
};
int main(void) {
  Derived d;
  d.show();
  return 0;
}
```

**(A)** i = 0 j = 0
**(B)** 编译器错误:I 和 j 在 Base
**(C)** 编译器错误:无法调用 Base

**的构造函数答案:****(B)**

**解释:**

[本题竞猜](https://www.geeksforgeeks.org/quiz-corner-gq/)