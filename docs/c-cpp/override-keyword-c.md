# 覆盖 C++ 中的关键字

> 原文:[https://www.geeksforgeeks.org/override-keyword-c/](https://www.geeksforgeeks.org/override-keyword-c/)

[函数覆盖](https://www.geeksforgeeks.org/function-overloading-vs-function-overriding-in-cpp/)是用相同的签名，即返回类型和参数，在其派生类中重新定义基类函数。
但是可能会有程序员在重写该函数时出错的情况。因此，为了跟踪这样的错误，C++ 11 提出了关键字 override。它将使编译器检查基类，看看是否有一个具有这个确切签名的虚函数。如果没有，编译器会显示一个错误。

从下面的例子可以更清楚地看出这一点:

```cpp
// A CPP program without override keyword. Here
// programmer makes a mistake and it is not caught.
#include <iostream>
using namespace std;

class Base {
public:

    // user wants to override this in
    // the derived class
    virtual void func() {
        cout << "I am in base" << endl;
    }
};

class derived : public Base {
public:
    // did a silly mistake by putting
    // an argument "int a"
    void func(int a) {
        cout << "I am in derived class" << endl;
    }
};

// Driver code
int main()
{
    Base b;
    derived d;
    cout << "Compiled successfully" << endl;
    return 0;
}
```

输出:

```cpp
Compiled successfully

```

**解释**:这里用户打算覆盖派生类中的 func()函数，但是做了一个愚蠢的错误，用不同的签名重新定义了函数。编译器没有检测到。然而，程序实际上并不是用户想要的。所以，为了避免这样愚蠢的错误，可以使用 override 关键字。
下面是一个 C++ 例子，展示了在 C++ 中 override 关键字的使用。

```cpp
// A CPP program that uses override keyword so
// that any difference in function signature is
// caught during compilation.
#include <iostream>
using namespace std;

class Base {
public:

    // user wants to override this in 
    // the derived class
    virtual void func() 
    {
        cout << "I am in base" << endl;
    }
};

class derived : public Base {
public:

    // did a silly mistake by putting 
    // an argument "int a"
    void func(int a) override 
    {
        cout << "I am in derived class" << endl;
    }
};

int main()
{
    Base b;
    derived d;
    cout << "Compiled successfully" << endl;
    return 0;
}
```

输出:

```cpp
prog.cpp:17:7: error: 'void derived::func(int)'
marked 'override', but does not override
  void func(int a) override 
       ^

```

简而言之，它具有以下功能。它有助于检查:

*   父类中有一个同名的方法。
*   父类中的方法被声明为“virtual”，这意味着它打算被重写。
*   父类中的方法与子类中的方法具有相同的签名。

本文由 [**MAZHAR IMAM KHAN**](https://www.linkedin.com/in/mazhar-imam-khan-95a34ab3/) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。