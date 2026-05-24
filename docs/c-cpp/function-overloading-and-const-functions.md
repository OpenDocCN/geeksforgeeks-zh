# 函数重载和 const 关键字

> 原文:[https://www . geesforgeks . org/function-overload-and-const-functions/](https://www.geeksforgeeks.org/function-overloading-and-const-functions/)

预测后续 C++ 程序的输出。

```cpp
#include<iostream>
using namespace std;

class Test
{
protected:
    int x;
public:
    Test (int i):x(i) { }
    void fun() const
    {
        cout << "fun() const called " << endl;
    }
    void fun()
    {
        cout << "fun() called " << endl;
    }
};

int main()
{
    Test t1 (10);
    const Test t2 (20);
    t1.fun();
    t2.fun();
    return 0;
}
```

输出:上述程序编译运行良好，并产生以下输出。

```cpp
fun() called
fun() const called
```

“void fun() const”和“void fun()”这两个方法具有相同的签名，只是一个是 const，另一个不是。此外，如果我们仔细查看输出，我们会发现在 const 对象上调用了“const void fun()”，在非常规对象上调用了“void fun()”。
C++ 允许基于 const 类型重载成员方法。当函数返回引用或指针时，基于常量类型的重载会很有用。我们可以使一个函数常量，返回常量引用或常量指针，另一个非常量函数，返回非常量引用或指针。详见[本](http://www.parashift.com/c++-faq-lite/const-overloading.html)。

**参数呢？**
与常量参数相关的规则很有意思。让我们先来看看下面两个例子。程序 1 编译失败，但程序 2 编译运行良好。

```cpp
// PROGRAM 1 (Fails in compilation)
#include<iostream>
using namespace std;

void fun(const int i)
{
    cout << "fun(const int) called ";
}
void fun(int i)
{
    cout << "fun(int ) called " ;
}
int main()
{
    const int i = 10;
    fun(i);
    return 0;
}
```

输出:

```cpp
Compiler Error: redefinition of 'void fun(int)'
```

```cpp
// PROGRAM 2 (Compiles and runs fine)
#include<iostream>
using namespace std;

void fun(char *a)
{
  cout << "non-const fun() " << a;
}

void fun(const char *a)
{
  cout << "const fun() " << a;
}

int main()
{
  const char *ptr = "GeeksforGeeks";
  fun(ptr);
  return 0;
}
```

输出:

```cpp
const fun() GeeksforGeeks
```

只有当常量参数是引用或指针时，C++ 才允许基于常量参数重载函数。这就是为什么程序 1 编译失败，但程序 2 运行良好的原因。这条规则实际上是有道理的。在程序 1 中，参数“I”是通过值传递的，因此 fun()中的“I”是 main()中“I”的副本。因此 fun()不能修改 main()的“I”。因此,“I”是作为常量参数还是普通参数接收并不重要。当我们通过引用或指针传递时，我们可以修改引用或指向的值，所以我们可以有两个版本的函数，一个可以修改引用或指向的值，另一个不能。

作为练习，预测以下程序的输出。

```cpp
#include<iostream>
using namespace std;

void fun(const int &i)
{
    cout << "fun(const int &) called ";
}
void fun(int &i)
{
    cout << "fun(int &) called " ;
}
int main()
{
    const int i = 10;
    fun(i);
    return 0;
}
```

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。