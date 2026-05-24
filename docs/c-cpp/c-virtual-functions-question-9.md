# C++ |虚函数|问题 9

> 原文:[https://www . geesforgeks . org/c-virtual-functions-question-9/](https://www.geeksforgeeks.org/c-virtual-functions-question-9/)

析构函数可以是虚拟的吗？

下面的程序会编译吗？

```cpp
#include <iostream>
using namespace std;
class Base {
public:
  virtual ~Base() {}   
};
int main() {
   return 0;
}
```

**(A)** 是
**(B)** 否

**回答:** **(A)**

**说明:**一个析构器可以是虚的。当基类指针指向派生类对象并且我们删除该对象时，我们可能需要调用适当的析构函数。如果析构函数不是虚拟的，那么只能调用基类析构函数。例如，考虑以下程序。

```cpp
// Not good code as destructor is not virtual
#include<iostream>
using namespace std;

class Base  {
public:
    Base()    { cout << "Constructor: Base" << endl; }
    ~Base()   { cout << "Destructor : Base" << endl; }
};

class Derived: public Base {
public:
    Derived()   { cout << "Constructor: Derived" << endl; }
    ~Derived()   { cout << "Destructor : Derived" << endl; }
};

int main()  {
    Base *Var = new Derived();
    delete Var;
    return 0;
}

Output on GCC:
Constructor: Base
Constructor: Derived
Destructor : Base

```

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)