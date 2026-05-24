# C++ |这个指针|问题 4

> 原文:[https://www.geeksforgeeks.org/c-this-pointer-question-4/](https://www.geeksforgeeks.org/c-this-pointer-question-4/)

预测后续 C++ 程序的输出

```cpp
#include<iostream>
using namespace std;

class Test
{
private:
  int x;
  int y;
public:
  Test(int x = 0, int y = 0) { this->x = x; this->y = y; }
  static void fun1() { cout << "Inside fun1()"; }
  static void fun2() { cout << "Inside fun2()"; this->fun1(); }
};

int main()
{
  Test obj;
  obj.fun2();
  return 0;
}
```

**(A)** 内 fun2()内 fun1()
**(B)** 内 fun2()
**(C)** 内 fun1()内 fun2()
**(D)** 编译器错误

**答案:****(D)**

**解释:**fun 2()有错误。它是一个静态函数，试图访问这个指针。

静态成员函数不能使用这个指针，因为静态成员函数可以在没有任何对象的情况下调用。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)