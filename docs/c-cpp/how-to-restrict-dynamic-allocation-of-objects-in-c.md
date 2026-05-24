# c++ 中如何限制对象的动态分配？

> 原文:[https://www . geeksforgeeks . org/如何限制 c 中对象的动态分配/](https://www.geeksforgeeks.org/how-to-restrict-dynamic-allocation-of-objects-in-c/)

C++ 编程语言允许自动(或堆栈分配)和动态分配对象。在 java & C#中，必须使用 new 动态分配所有对象。
出于运行时效率的考虑，C++ 支持栈分配对象。基于堆栈的对象由 C++ 编译器隐式管理。它们在超出范围时被销毁，动态分配的对象必须使用 delete 操作符手动释放，否则会发生内存泄漏。C++ 不支持像 Java & C#这样的语言使用的自动垃圾收集方法。

**我们如何在 C++ 中实现类“Test”的以下行为？**

```cpp
Test* t = new Test; // should produce compile time error
Test t;    // OK 
```

的思想是保持新的运算符函数私有，这样就不能调用 new。请参见以下程序。无法使用 new 创建“测试”类的对象，因为新运算符函数在“测试”中是私有的。如果我们取消 main()第二行的注释，程序将产生编译时错误。

```cpp
#include <iostream>
using namespace std;

// Objects of Test can not be dynamically allocated
class Test
{
    // Notice this, new operator function is private
    void* operator new(size_t size);
    int x;
public:
    Test()          { x = 9; cout << "Constructor is called\n"; }
    void display()  { cout << "x = " << x << "\n";  }
    ~Test()         { cout << "Destructor is executed\n"; }
};

int main()
{
    // Uncommenting following line would cause a compile time error.
    // Test* obj=new Test();
    Test t;          // Ok, object is allocated at compile time
    t.display();
    return 0;
} // object goes out of scope, destructor will be called
```

输出:

```cpp
Constructor is called
x = 9
Destructor is executed
```

**参考:**
[c++ 的设计与进化，比雅尼·斯特劳斯特鲁普](http://www.amazon.com/gp/product/0201543303/ref=as_li_qf_sp_asin_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=0201543303&linkCode=as2&tag=geeksf0f-20) ![](http://ir-na.amazon-adsystem.com/e/ir?t=geeksf0f-20&l=as2&o=1&a=0201543303)

本文由 **Pravasi Meet** 供稿。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。