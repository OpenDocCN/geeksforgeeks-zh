# c++ 中的对象委托

> 原文:[https://www.geeksforgeeks.org/object-delegation-in-cpp/](https://www.geeksforgeeks.org/object-delegation-in-cpp/)

**简介:**

*   Every programming language based on object-oriented concepts tries to relate everything to the real world.
*   Similarly, C++ language uses [class](https://www.geeksforgeeks.org/c-classes-and-objects/) , [inheritance](https://www.geeksforgeeks.org/inheritance-in-c/) , [polymorphism](https://www.geeksforgeeks.org/polymorphism-in-c/) to connect concepts with real-world concepts.
*   In this article, the topic of discussion will be what object delegation is in C++ and the use of object delegation in C++.

**c++ 中的对象委托:**对象委托是指使用另一个类的对象作为另一个类的类成员。它被称为对象委托。下面是委托的一些属性:

*   Delegate can be a substitute for inheritance, but in inheritance, there is an i-s a relationship, but in delegation, there is no inheritance relationship between classes.
*   Delegates allow us to use the properties of a specific class that we need in the class.
*   Delegate can be regarded as a relationship between objects, in which one object forwards a method call to another object, which is called its delegate.
*   The main advantage of delegates is the flexibility of runtime-delegates can be easily changed at runtime.
*   However, unlike inheritance, delegation is not directly supported by most popular object-oriented languages, and it is not conducive to [dynamic polymorphism](https://www.geeksforgeeks.org/dynamic-method-dispatch-runtime-polymorphism-java/) .

下面是说明对象委托的 C++ 程序:

## c++

```cpp
// C++ program to illustrate the
// Object Delegation
#include <iostream>
using namespace std;
class First {
public:
    void print() { cout << "The Delegate"; }
};
class Second {
    // Creating instance of the class
    First ob;

public:
    void print() { ob.print(); }
};

// Driver Code
int main()
{
    Second ob1;
    ob1.print();
    return 0;
}
```

**输出:**

```cpp
The Delegate
```

**什么时候用什么？**

下面是一些使用继承或委托的例子:

*   Suppose the class is called B, and the class derived/entrusted to [is called A. 。](https://www.geeksforgeeks.org/c-classes-and-objects/)
*   If the user wants to express a relationship (is-a), then use inheritance.
*   The user wants to be able to pass the class to the existing API expecting A, and then use [to inherit](https://www.geeksforgeeks.org/inheritance-in-c/) .
*   Users want to enhance A, but A is final, and can't be further subdivided except using [to synthesize](https://www.geeksforgeeks.org/association-composition-aggregation-java/) and entrustment.