# C++ |这个指针|问题 3

> 原文:[https://www.geeksforgeeks.org/c-this-pointer-question-3/](https://www.geeksforgeeks.org/c-this-pointer-question-3/)

预测后续 C++ 程序的输出。

```cpp
#include<iostream>
using namespace std;

class Test
{
private:
  int x;
public:
  Test(int x = 0) { this->x = x; }
  void change(Test *t) { this = t; }
  void print() { cout << "x = " << x << endl; }
};

int main()
{
  Test obj(5);
  Test *ptr = new Test (10);
  obj.change(ptr);
  obj.print();
  return 0;
}
```

**(A)**x = 5
**(B)**x = 10
**(C)**编译器错误
**(D)** 运行时错误

**答案:****(C)**

**解释:**这是一个常量指针，所以第“this = t；”行有错误

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)