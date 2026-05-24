# C++ |析构函数|问题 4

> 原文:[https://www.geeksforgeeks.org/c-destructors-question-4/](https://www.geeksforgeeks.org/c-destructors-question-4/)

```cpp
#include <iostream>
using namespace std; 
class A
{
    int id;
    static int count;
public:
    A() {
        count++ ;
        id = count;
        cout << "constructor for id " << id << endl;
    }
    ~A() {
        cout << "destructor for id " << id << endl;
    }
};

int A::count = 0;

int main() {
    A a[3];
    return 0;
}
```

**(甲)**

```cpp
constructor for id 1
constructor for id 2
constructor for id 3
destructor for id 3
destructor for id 2
destructor for id 1
```

**(B)**

```cpp
constructor for id 1
constructor for id 2
constructor for id 3
destructor for id 1
destructor for id 2
destructor for id 3
```

**(C)**

```cpp
Compiler Dependent.
```

**(D)**

```cpp
constructor for id 1
destructor for id 1
```

**回答:** **(A)**

**说明:**在上面的程序中，id 是一个静态变量，它随着每个对象的创建而递增。首先创建对象 a[0]，但首先销毁对象 a[2]。对象总是按照与创建相反的顺序被销毁。颠倒顺序的原因是，以后创建的对象可能会使用以前创建的对象。例如，考虑下面的代码片段。

```cpp
A a;
B b(a);
```

在上面的代码中，对象“b”(在“a”之后创建)可能会在内部使用“a”的一些成员。所以在“b”之前破坏“a”可能会产生问题。因此，对象“b”必须在“a”之前销毁。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)