# C++ | Misc C++ |问题 3

> 原文:[https://www.geeksforgeeks.org/c-misc-c-question-3/](https://www.geeksforgeeks.org/c-misc-c-question-3/)

预测后续 C++ 程序的输出

```cpp
#include<iostream>
using namespace std;

union A {
  int a;
  unsigned int b;
  A() { a = 10; }
  unsigned int getb() {return b;}
};

int main()
{
    A obj;
    cout << obj.getb();
    return 0;
}
```

**(A)** 编译器错误:union 不能有函数
**(B)** 编译器错误:不能访问 A 的私有成员
**(C)**10
**(D)**垃圾值

**答案:****(C)**

**解释:**像 struct 和 class 一样，union 可以有方法。与 struct 一样，与 class 不同，union 的成员在默认情况下是公共的。

由于联盟的数据成员共享内存，b 的值变为与 a 相同。

[本题测验](https://www.geeksforgeeks.org/quiz-corner-gq/)