# c++ 中的 RTTI(运行时类型信息)

> 原文:[https://www.geeksforgeeks.org/g-fact-33/](https://www.geeksforgeeks.org/g-fact-33/)

在 C++ 中，RTTI(运行时类型信息)是一种在运行时公开对象数据类型信息的机制，并且只对至少有一个虚函数的类可用。它允许在程序执行期间确定对象的类型

例如，dynamic_cast 使用 RTTI，并且由于基类 B 中没有虚函数，随后的程序失败，并出现错误“无法将 dynamic_cast `b '(类型为` class B* ')转换为 type `class D* '(源类型不是多态的)。”

```cpp
// CPP program to illustrate 
// Run Time Type Identification 
#include<iostream>
using namespace std;
class B { };
class D: public B {};

int main()
{
    B *b = new D;
    D *d = dynamic_cast<D*>(b);
    if(d != NULL)
        cout<<"works";
    else
        cout<<"cannot cast B* to D*";
    getchar();
    return 0;
}
```

向基类 B 添加一个虚函数使其工作。

```cpp
// CPP program to illustrate 
// Run Time Type Identification 
#include<iostream>
using namespace std;
class B { virtual void fun() {} };
class D: public B { };

int main()
{
    B *b = new D;
    D *d = dynamic_cast<D*>(b);
    if(d != NULL)
        cout << "works";
    else
        cout << "cannot cast B* to D*";
    getchar();
    return 0;
}
```

输出:

```cpp
works
```

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。