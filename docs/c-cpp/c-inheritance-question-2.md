# C++ |继承|问题 2

> 原文:[https://www.geeksforgeeks.org/c-inheritance-question-2/](https://www.geeksforgeeks.org/c-inheritance-question-2/)

输出？

```cpp
#include <iostream>  
using namespace std;

class Base1 {
 public:
     ~Base1()  { cout << " Base1's destructor" << endl; }
};

class Base2 {
 public:
     ~Base2()  { cout << " Base2's destructor" << endl; }
};

class Derived: public Base1, public Base2 {
   public:
     ~Derived()  { cout << " Derived's destructor" << endl; }
};

int main()
{
   Derived d;
   return 0;
}
```

**(甲)**

```cpp
Base1's destructor
Base2's destructor
Derived's destructor
```

**(B)**

```cpp
Derived's destructor
Base2's destructor
Base1's destructor

```

**(C)**

```cpp
Derived's destructor
```

**(D)** 依赖编译器

**回答:** **(B)**

**说明:**析构函数总是按照构造函数的逆序调用。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)