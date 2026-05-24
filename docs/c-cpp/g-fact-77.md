# c++ 中“this”指针的类型

> 原文:[https://www.geeksforgeeks.org/g-fact-77/](https://www.geeksforgeeks.org/g-fact-77/)

在 C++ 中， [*这个*指针](http://publib.boulder.ibm.com/infocenter/comphelp/v8v101/index.jsp?topic=%2Fcom.ibm.xlcpp8a.doc%2Flanguage%2Fref%2Fcplr035.htm)作为隐藏参数传递给所有非静态成员函数调用。*这个*的类型取决于函数声明。如果一个类的成员函数 *X* 声明为 *const* ，*这个*的类型为 *const X*(见下面的代码 1)*如果成员函数声明为 *volatile* ，这个的类型为 *volatile X** (见下面的代码 2)，如果成员函数声明为 *const volatile* ，这个的类型为

*代码 1*

```cpp
*#include<iostream>
class X {
   void fun() const {

    // this is passed as hidden argument to fun().
    // Type of this is const X* const
    }
};*
```

*代码 2*

```cpp
*#include<iostream>
class X {
   void fun() volatile {

     // this is passed as hidden argument to fun().
     // Type of this is volatile X* const
    }
};*
```

*代码 3*

```cpp
*#include<iostream>
class X {
   void fun() const volatile {

     // this is passed as hidden argument to fun().
     // Type of this is const volatile X* const
    }
};*
```

*参考文献:
[http://www . open-STD . org/JTC 1/sc22/wg21/docs/papers/2005/n 1905 . pdf](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2005/n1905.pdf)*

*如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。*