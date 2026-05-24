# c++ 中什么时候调用复制构造函数？

> 原文:[https://www . geesforgeks . org/当-is-a-copy-constructor-in-CPP/](https://www.geeksforgeeks.org/when-is-a-copy-constructor-called-in-cpp/)

[复制构造函数](https://www.geeksforgeeks.org/copy-constructor-in-cpp/)是一个成员函数，它使用同一类的另一个对象初始化一个对象。复制构造函数主要在从现有对象创建新对象时调用，作为现有对象的副本。

**在 C++ 中，在以下情况下可以调用复制构造函数:**

**1)** 当类的一个对象通过值返回时。
**2)** 当类的一个对象通过值作为参数传递(给一个函数)时。
**3)** 当一个对象是基于同一类的另一个对象构造的。
**4)** 编译器生成临时对象时。

**示例:**

## C++

```cpp
// CPP Program to demonstrate the use of copy constructor
#include <iostream>
#include <stdio.h>
using namespace std;

class storeVal {
public:
    // Constructor
    storeVal() {}
    // Copy Constructor
    storeVal(const storeVal& s)
    {
        cout << "Copy constructor has been called " << endl;
    }
};

// Driver code
int main()
{
    storeVal obj1;
    storeVal obj2 = obj1;
    getchar();
    return 0;
}
```

**Output**

```cpp
Copy constructor has been called 
```

然而，不能保证在所有这些情况下都会调用复制构造函数，因为 C++ 标准允许编译器在某些情况下优化复制，一个例子是**返回值优化**(有时称为 **RVO** )。

> **注意:**如果类中没有定义复制构造函数，C++ 编译器会隐式提供复制构造函数。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。