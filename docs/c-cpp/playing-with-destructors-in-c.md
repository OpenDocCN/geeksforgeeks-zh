# 在 C++ 中玩析构函数

> 原文:[https://www . geeksforgeeks . org/c-in-c 玩析构函数/](https://www.geeksforgeeks.org/playing-with-destructors-in-c/)

预测下面代码片段的输出。

```cpp
#include <iostream>
using namespace std;

int i;

class A
{
public:
    ~A()
    {
        i=10;
    }
};

int foo()
{
    i=3;
    A ob;
    return i;
}

int main()
{
    cout << "i = " << foo() << endl;
    return 0;
}
```

上述程序的输出为“i = 3”。
*为什么输出是 i= 3 而不是 10？*
从函数返回时，析构函数是最后执行的方法。对象“ob”的析构函数在 I 的值被复制到函数的返回值后被调用。因此，在析构函数将 I 的值更改为 10 之前，I 的当前值被复制&因此输出为 i = 3。

*如何让程序输出“i = 10”？*
以下是返回更新值的两种方式:

*1)通过引用返回:*
由于引用给出了变量的 l 值，通过使用引用返回，程序将输出“i = 10”。

```cpp
#include <iostream>
using namespace std;

int i;

class A
{
public:
    ~A()
    {
        i = 10;
    }
};

int& foo()
{
    i = 3;
    A ob;
    return i;
}

int main()
{
    cout << "i = " << foo() << endl;
    return 0;
}
```

函数 foo()返回变量 I 的 l 值。因此，I 的地址将被复制到返回值中。因为，引用会自动取消引用。它将输出“i = 10”。

*2。在块范围内创建对象 ob*

```cpp
#include <iostream>
using namespace std;

int i;

class A
{
public:
    ~A()
    {
        i = 10;
    }
};

int foo()
{
    i = 3;
    {
        A ob;
    }
    return i;
}

int main()
{
    cout << "i = " << foo() << endl;
    return 0;
}
```

由于对象 ob 是在块范围内创建的，因此在块结束后将调用对象的析构函数，从而将 I 的值更改为 10。最后将 10 复制到返回值中。

本文由**阿卡西·巴恩瓦尔**编辑，GeeksforGeeks 团队审核。如果您发现任何不正确的地方，或者您想分享关于上面讨论的主题的更多信息，请写评论