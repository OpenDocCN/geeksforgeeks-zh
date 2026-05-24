# c++ 中的堆栈展开

> 原文:[https://www.geeksforgeeks.org/stack-unwinding-in-c/](https://www.geeksforgeeks.org/stack-unwinding-in-c/)

**栈展开**是在运行时从函数调用栈中移除函数项的过程。本地对象按照与构建时相反的顺序被销毁。

堆栈展开一般与[异常处理](https://www.geeksforgeeks.org/exception-handling-c/)相关。在 C++ 中，当发生异常时，函数调用堆栈会线性搜索异常处理程序，并且带有异常处理程序的函数之前的所有条目都会从函数调用堆栈中移除。因此，如果异常没有在同一个函数中处理(在那里被抛出)，那么异常处理就涉及到堆栈展开。基本上，堆栈展开是一个为运行时构造的所有自动对象调用析构函数(每当抛出异常时)的过程。

***例如，以下程序的输出是:***

## CPP

```cpp
// CPP Program to demonstrate Stack Unwinding
#include <iostream>
using namespace std;

// A sample function f1() that throws an int exception
void f1() throw(int)
{
    cout << "\n f1() Start ";
    throw 100;
    cout << "\n f1() End ";
}

// Another sample function f2() that calls f1()
void f2() throw(int)
{
    cout << "\n f2() Start ";
    f1();
    cout << "\n f2() End ";
}

// Another sample function f3() that calls f2() and handles
// exception thrown by f1()
void f3()
{
    cout << "\n f3() Start ";
    try {
        f2();
    }
    catch (int i) {
        cout << "\n Caught Exception: " << i;
    }
    cout << "\n f3() End";
}

// Driver Code
int main()
{
    f3();

    getchar();
    return 0;
}
```

**输出**

```cpp
 f3() Start 
 f2() Start 
 f1() Start 
 Caught Exception: 100
 f3() End
```

**说明:**

*   当 f1()抛出异常时，它的条目将从函数调用堆栈中删除，因为 f1()不包含抛出异常的异常处理程序，那么调用堆栈中的下一个条目将查找异常处理程序。
*   下一个条目是 f2()。因为 f2()也没有处理程序，所以它的条目也从函数调用堆栈中移除。
*   函数调用堆栈中的下一个条目是 f3()。因为 f3()包含一个异常处理程序，所以 f3()中的 catch 块被执行，最后，catch 块之后的代码被执行。

请注意，f1()和 f2()中的以下行根本没有执行。

```cpp
 cout<<"\n f1() End ";  // inside f1()

 cout<<"\n f2() End ";  // inside f2()
```

如果 f1()和 f2()中有一些本地类对象，那么这些本地对象的析构函数将在堆栈展开过程中被调用。

> **注意:**当异常没有在同一个函数中处理时，Java 中也会发生堆栈展开。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。