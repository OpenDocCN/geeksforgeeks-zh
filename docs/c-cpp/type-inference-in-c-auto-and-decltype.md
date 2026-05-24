# c++ 中的类型推断(自动和去类型)

> 原文:[https://www . geesforgeks . org/type-推断-in-c-auto-and-decltype/](https://www.geeksforgeeks.org/type-inference-in-c-auto-and-decltype/)

**类型推断**是指在编程语言中自动推导表达式的数据类型。在 C++ 11 之前，每个数据类型都需要在编译时显式声明，在运行时限制表达式的值，但是在 C++ 的新版本之后，包含了许多关键字，这使得程序员可以将类型推导留给编译器本身。

有了类型推断功能，我们可以花更少的时间写出编译器已经知道的东西。因为所有的类型都是在编译阶段推导出来的，所以编译的时间会稍微增加，但是不会影响程序的运行时间。

**1) auto 关键字:**auto 关键字指定正在声明的变量的类型将自动从其初始值中扣除。就函数而言，如果它们的返回类型是 auto，那么它将在运行时由返回类型表达式进行计算。auto 的良好用途是在为容器创建迭代器时避免长时间初始化。

> **注意:**用 auto 关键字声明的变量应该只在声明时初始化，否则会出现编译时错误。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate working of auto
// and type inference

#include <bits/stdc++.h>
using namespace std;

int main()
{
    // auto a; this line will give error
    // because 'a' is not initialized at
    // the time of declaration
    // a=33;

    // see here x ,y,ptr are
    // initialised at the time of
    // declaration hence there is
    // no error in them
    auto x = 4;
    auto y = 3.37;
    auto ptr = &x;
    cout << typeid(x).name() << endl
         << typeid(y).name() << endl
         << typeid(ptr).name() << endl;

    return 0;
}
```

**Output**

```cpp
i
d
Pi
```

> **注意:**我们使用了 **typeid** 来获取变量的类型。

**Typeid** 是一个运算符，用于需要知道对象动态类型的地方。

*typeid(x)。name()返回 x 的数据类型，例如，它返回“I”代表整数，“d”代表双精度，“Pi”代表指向整数的指针等。但是返回的实际名称主要依赖于编译器。*

***auto 的良好用法是在为容器创建迭代器时避免长时间初始化。**T3】*

## C++

```cpp
// C++ program to demonstrate that we can use auto to
// save time when creating iterators

#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Create a set of strings
    set<string> st;
    st.insert({ "geeks", "for", "geeks", "org" });

    // 'it' evaluates to iterator to set of string
    // type automatically
    for (auto it = st.begin(); it != st.end(); it++)
        cout << *it << " ";

    return 0;
}
```

**Output**

```cpp
for geeks org 
```

> **注意:**如果分配了整数引用，auto 就会变成 int 类型。为了使其成为参考类型，我们使用自动&。
> 
> *   返回对 int 类型的引用的函数:int & fun(){ }；
> *   m 将默认为 int 类型，而不是 int & type:auto m = fun()；
> *   n 将为 int& type，因为使用了 extra & with auto 关键字:auto & n = fun()；

**2) decltype 关键字:**检查实体的声明类型或表达式的类型。“auto”允许您声明具有特定类型的变量，而 decltype 允许您从变量中提取类型，因此 decltype 是一种运算符，用于计算传递的表达式的类型。
上述关键词及其用法说明如下:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate use of decltype
#include <bits/stdc++.h>
using namespace std;

int fun1() { return 10; }
char fun2() { return 'g'; }

int main()
{
    // Data type of x is same as return type of fun1()
    // and type of y is same as return type of fun2()
    decltype(fun1()) x;
    decltype(fun2()) y;

    cout << typeid(x).name() << endl;
    cout << typeid(y).name() << endl;

    return 0;
}
```

**Output**

```cpp
i
c
```

下面再举一个例子来演示 **decltype** 的使用，

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate use of decltype
#include <bits/stdc++.h>
using namespace std;

// Driver Code
int main()
{
    int x = 5;

    // j will be of type int : data type of x
    decltype(x) j = x + 5;

    cout << typeid(j).name();

    return 0;
}
```

**Output**

```cpp
i
```

#### **一个演示自动和检测类型使用的程序**

下面是一个 [C++ 模板](https://www.geeksforgeeks.org/templates-cpp/)函数 **min_type()** ，返回两个数字的最小值。这两个数字可以是任何整数类型。使用最小二乘类型确定返回类型。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate use of decltype in functions
#include <bits/stdc++.h>
using namespace std;

// A generic function which finds minimum of two values
// return type is type of variable which is minimum
template <class A, class B>
auto findMin(A a, B b) -> decltype(a < b ? a : b)
{
    return (a < b) ? a : b;
}

// driver function to test various inference
int main()
{
    // This call returns 3.44 of doubale type
    cout << findMin(4, 3.44) << endl;

    // This call returns 3 of double type
    cout << findMin(5.4, 3) << endl;

    return 0;
}
```

**Output**

```cpp
3.44
3
```

**落叶与类型**

*   Decltype 在编译时给出类型信息，而 typeid 在运行时给出。
*   因此，如果我们有一个基类引用(或指针)引用(或指向)一个派生类对象，decltype 会给出 type 作为基类引用(或指针，但是 typeid 会给出派生类引用(或指针)。

本文由 **Utkarsh Trivedi** 供稿。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。