# 如何制作一个对象只能动态分配的 C++ 类？

> 原文:[https://www . geesforgeks . org/make-class-其对象可以动态分配/](https://www.geeksforgeeks.org/make-class-whose-objects-can-dynamically-allocated/)

问题是创建一个类，使得对象的非动态分配导致编译器错误。例如，使用以下规则创建一个“测试”类。

```cpp
Test t1;  // Should generate compiler error
Test *t3 = new Test; // Should work fine
```

想法是在类中创建一个[私有析构函数](https://www.geeksforgeeks.org/private-destructor/)。当我们创建一个私有析构函数时，编译器会为非动态分配的对象生成一个编译器错误，因为一旦它们不被使用，编译器就需要将它们从堆栈段中移除。
由于编译器不负责动态分配对象的解除分配(程序员应该显式解除分配)，编译器不会对它们有任何问题。为了避免内存泄漏，我们创建了一个朋友函数*destrust()*，类的用户可以调用这个函数来销毁对象。

```cpp
#include <iostream>
using namespace std;

// A class whose object can only be dynamically created
class Test
{
private:
    ~Test() { cout << "Destroying Object\n"; }
public:
     Test() { cout << "Object Created\n"; }
friend void destructTest(Test* );
};

// Only this function can destruct objects of Test
void destructTest(Test* ptr)
{
    delete ptr;
    cout << "Object Destroyed\n";
}

int main()
{
    /* Uncommenting following following line would cause compiler error */
    // Test t1;

    // create an object
    Test *ptr = new Test;

    // destruct the object to avoid memory leak
    destructTest(ptr);

    return 0;
}
```

输出:

```cpp
Object Created
Destroying Object
Object Destroyed
```

如果不想创建友元函数，也可以在 Test 中重载 delete 和 delete[]运算符，这样就不用调用特定的函数来删除动态分配的对象。

如果您发现任何不正确的地方，或者您想分享关于上面讨论的主题的更多信息，请写评论