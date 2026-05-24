# c++ 中的 const _ cast |类型铸造运算符

> 原文:[https://www . geesforgeks . org/const _ cast-in-c-type-casting-operators/](https://www.geeksforgeeks.org/const_cast-in-c-type-casting-operators/)

C++ 支持以下 4 种类型的转换运算符:

1.const_cast
2。static_cast
3。动态 _ 投
4。重新解释 _cast

**1。const_cast**
const_cast 用于丢弃变量的常量。以下是一些关于 const_cast 的有趣事实。

**1)** const_cast 可用于更改 const 成员函数内部的非 const 类成员。考虑下面的代码片段。在 const member 函数 fun()中，“this”被编译器视为“const student* const this”，即“this”是指向常量对象的常量指针，因此编译器不允许通过“this”指针更改数据成员。const_cast 将“this”指针的类型更改为“student* const this”。

```cpp
#include <iostream>
using namespace std;

class student
{
private:
    int roll;
public:
    // constructor
    student(int r):roll(r) {}

    // A const function that changes roll with the help of const_cast
    void fun() const
    {
        ( const_cast <student*> (this) )->roll = 5;
    }

    int getRoll()  { return roll; }
};

int main(void)
{
    student s(3);
    cout << "Old roll number: " << s.getRoll() << endl;

    s.fun();

    cout << "New roll number: " << s.getRoll() << endl;

    return 0;
}
```

输出:

```cpp
Old roll number: 3
New roll number: 5
```

**2)** const_cast 可以用来将 const 数据传递给不接收 const 的函数。例如，在下面的程序中，fun()接收一个普通的指针，但是在 const_cast 的帮助下可以传递一个指向 const 的指针。

```cpp
#include <iostream>
using namespace std;

int fun(int* ptr)
{
    return (*ptr + 10);
}

int main(void)
{
    const int val = 10;
    const int *ptr = &val;
    int *ptr1 = const_cast <int *>(ptr);
    cout << fun(ptr1);
    return 0;
}
```

输出:

```cpp
20
```

**3)** 修改最初声明为常量的值是未定义的行为。考虑以下程序。程序的输出未定义。变量“val”是一个常量变量，调用“fun(ptr1)”试图使用 const_cast 修改“val”。

```cpp
#include <iostream>
using namespace std;

int fun(int* ptr)
{
    *ptr = *ptr + 10;
    return (*ptr);
}

int main(void)
{
    const int val = 10;
    const int *ptr = &val;
    int *ptr1 = const_cast <int *>(ptr);
    fun(ptr1);
    cout << val;
    return 0;
}
```

输出:

```cpp
 Undefined Behavior 
```

修改一个最初没有声明为常量的值是很好的。例如，在上面的程序中，如果我们从 val 的声明中移除 const，程序将产生 20 作为输出。

```cpp
#include <iostream>
using namespace std;

int fun(int* ptr)
{
    *ptr = *ptr + 10;
    return (*ptr);
}

int main(void)
{
    int val = 10;
    const int *ptr = &val;
    int *ptr1 = const_cast <int *>(ptr);
    fun(ptr1);
    cout << val;
    return 0;
}
```

**4)** const_cast 被认为比简单型铸造更安全。从这个意义上说，如果铸造的类型与原始物体不同，铸造就不会发生，这是比较安全的。例如，以下程序在编译时失败，因为“int *”正被类型转换为“char *”

```cpp
#include <iostream>
using namespace std;

int main(void)
{
    int a1 = 40;
    const int* b1 = &a1;
    char* c1 = const_cast <char *> (b1); // compiler error
    *c1 = 'A';
    return 0;
}
```

输出:

```cpp
prog.cpp: In function ‘int main()’:
prog.cpp:8: error: invalid const_cast from type 'const int*' to type 'char*'
```

**5)** const_cast 也可以用来施放掉波动属性。例如，在下面的程序中，b1 的 typeid 是 PVKi(指针指向一个易变的常数整数)，c1 的 typeid 是 Pi(指针指向整数)

```cpp
#include <iostream>
#include <typeinfo>
using namespace std;

int main(void)
{
    int a1 = 40;
    const volatile int* b1 = &a1;
    cout << "typeid of b1 " << typeid(b1).name() << '\n';
    int* c1 = const_cast <int *> (b1);
    cout << "typeid of c1 " << typeid(c1).name() << '\n';
    return 0;
}
```

输出:

```cpp
typeid of b1 PVKi
typeid of c1 Pi

```

**练习**
预测以下程序的输出。如果存在编译错误，请修复它们。

**问题 1**

```cpp
#include <iostream>
using namespace std;

int main(void)
{
    int a1 = 40;
    const int* b1 = &a1;
    char* c1 = (char *)(b1);
    *c1 = 'A';
    return 0;
}
```

**问题 2**

```cpp
#include <iostream>
using namespace std;

class student
{
private:
    const int roll;
public:
    // constructor
    student(int r):roll(r) {}

    // A const function that changes roll with the help of const_cast
    void fun() const
    {
        ( const_cast <student*> (this) )->roll = 5;
    }

    int getRoll()  { return roll; }
};

int main(void)
{
    student s(3);
    cout << "Old roll number: " << s.getRoll() << endl;

    s.fun();

    cout << "New roll number: " << s.getRoll() << endl;

    return 0;
}
```

——[阿瓦斯·巴恩瓦尔](http://www.facebook.com/barnwal.aashish)。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论