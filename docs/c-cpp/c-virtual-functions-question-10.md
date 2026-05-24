# C++ |虚函数|第 10 题

> 原文:[https://www . geesforgeks . org/c-virtual-functions-question-10/](https://www.geeksforgeeks.org/c-virtual-functions-question-10/)

```cpp
#include<iostream>
using namespace std;
class Base  {
public:
    Base()    { cout<<"Constructor: Base"<<endl; }
    virtual ~Base()   { cout<<"Destructor : Base"<<endl; }
};
class Derived: public Base {
public:
    Derived()   { cout<<"Constructor: Derived"<<endl; }
    ~Derived()  { cout<<"Destructor : Derived"<<endl; }
};
int main()  {
    Base *Var = new Derived();
    delete Var;
    return 0;
}
```

**(甲)**

```cpp
Constructor: Base
Constructor: Derived
Destructor : Derived
Destructor : Base
```

**(B)**

```cpp
Constructor: Base
Constructor: Derived
Destructor : Base
```

**(C)**

```cpp
Constructor: Base
Constructor: Derived
Destructor : Derived
```

**(D)**

```cpp
Constructor: Derived
Destructor : Derived
```

**回答:** **(A)**

**说明:**由于析构函数是虚的，所以调用派生类析构函数，派生类析构函数又调用基类析构函数。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)