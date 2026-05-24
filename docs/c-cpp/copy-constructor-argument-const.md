# 为什么 C++ 中复制构造函数参数应该是 const？

> 原文:[https://www . geesforgeks . org/copy-constructor-argument-const/](https://www.geeksforgeeks.org/copy-constructor-argument-const/)

当我们创建自己的复制构造函数时，我们通过引用传递一个对象，我们通常将其作为常量引用传递。
传递 const 引用的一个原因是，我们应该尽可能在 C++ 中使用 const，这样对象就不会被意外修改。这是将引用作为常量传递的一个很好的理由，但还有更多。比如预测下面 C++ 程序的输出。假设[复制省略](https://www.geeksforgeeks.org/copy-elision-in-c/)不是由编译器完成的。

```cpp
#include<iostream>
using namespace std;

class Test
{
   /* Class data members */ 
public:
   Test(Test &t) { /* Copy data members from t*/}
   Test()        { /* Initialize data members */ }
};

Test fun()
{
    cout << "fun() Called\n";
    Test t;
    return t;
}

int main()
{
    Test t1;
    Test t2 = fun();
    return 0;
}
```

输出:

```cpp
 Compiler Error in line "Test t2 = fun();" 
```

这个程序乍一看很好，但它有编译器错误。如果我们在复制构造函数中添加 const，程序可以正常工作，也就是说，我们将复制构造函数改为如下。

```cpp
Test(const Test &t) { cout << "Copy Constructor Called\n"; }
```

或者如果我们更改行“Test T2 = fun()；”接下来的两行，程序也运行良好。

```cpp
Test t2; 
t2 = fun();
```

fun()函数按值返回。因此编译器创建了一个临时对象，并在原始程序中使用复制构造函数将其复制到 t2(临时对象作为参数传递给复制构造函数)。编译器错误的原因是，编译器创建的临时对象不能绑定到非常数引用，并且原始程序试图这样做。修改编译器创建的临时对象是没有意义的，因为它们随时可能死亡。

本文由 **Abhay Rathi** 整理。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论