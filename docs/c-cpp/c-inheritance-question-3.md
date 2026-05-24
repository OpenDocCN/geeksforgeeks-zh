# C++ |继承|问题 3

> 原文:[https://www.geeksforgeeks.org/c-inheritance-question-3/](https://www.geeksforgeeks.org/c-inheritance-question-3/)

假设一个整数需要 4 个字节，并且在下面的类中没有对齐，预测输出。

```cpp
#include<iostream>
using namespace std;

class base {
    int arr[10];
};

class b1: public base { };

class b2: public base { };

class derived: public b1, public b2 {};

int main(void)
{
  cout << sizeof(derived);
  return 0;
}
```

**(A)**40
**(B)**80
**(C)**0
**(D)**4

**答案:****(B)**

**说明:**既然 b1 和 b2 都是从类基继承而来，那么类基的两个副本就存在于类派生之中。这种没有虚拟的继承造成了空间的浪费和歧义。在这种情况下，虚拟基类用于节省空间和避免歧义。例如，以下程序打印 48。8 个额外字节用于编译器存储的簿记信息(详情见此)

```cpp
#include<iostream>
using namespace std;

class base {
  int arr[10];     
};

class b1: virtual public base { };

class b2: virtual public base { };

class derived: public b1, public b2 {};

int main(void)
{ 
  cout << sizeof(derived);
  return 0;
} 
```

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)