# 用 C++ 打印 1 到 100，没有循环和递归

> 原文:[https://www.geeksforgeeks.org/output-of-c-program-set-18-3/](https://www.geeksforgeeks.org/output-of-c-program-set-18-3/)

下面是一个 C++ 程序，在没有循环和递归的情况下打印 1 到 100。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
using namespace std;

template<int N>
class PrintOneToN
{
public:
    static void print()
    {
        PrintOneToN<N-1>::print();  // Note that this is not recursion
        cout << N << endl;
    }
};

template<>
class PrintOneToN<1>
{
public:
    static void print()
    {
        cout << 1 << endl;
    }
};
int main()
{
    const int N = 100;
    PrintOneToN<N>::print();
    return 0;
}
```

输出:

```cpp
1
2
3
..
..
98
99
100
```

该程序打印从 1 到 n 的所有数字，而不使用循环和递归。这个程序使用的概念是[模板元编程](https://www.geeksforgeeks.org/template-metaprogramming-in-c/)。
让我们看看这是如何运作的。[c++ 中的模板](http://en.wikipedia.org/wiki/Template_(C%2B%2B))允许非数据类型也作为参数。非数据类型意味着值，而不是数据类型。例如，在上面的程序中，N 作为非数据类型的值传递。为每个参数创建一个泛型类的新实例，这些类是在编译时创建的。在上面的程序中，当编译器看到 N = 100 的语句“printoneon<>::print()”时，它会创建一个实例 printoneon<100>。在函数 printonet on<100>:print()中，调用了另一个函数 printonet on<99>:print()，因此创建了一个实例 PrintOneToN < 99 >。同样，从 PrintOneToN < 100 >到 PrintOneToN < 2 >的所有实例都将被创建。print one ton<1>:print()已经在那里，打印 1。函数 PrintOneToN < 2 >打印 2 等等。因此，我们将从 1 到 N 的所有数字都打印在屏幕上。
接下来是**另一种方法**打印 1 到 100，没有循环和递归。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include<iostream>
using namespace std;

class A
{
public:
    static int a;
    A()
    {  cout<<a++ <<endl;  }
};

int A::a = 1;

int main()
{
    int N = 100;
    A obj[N];
    return 0;
}
```

该程序的输出与上述程序相同。在上面的程序中，类 A 有一个静态变量“A”，它随着类 A 的每个实例而递增。类 A 的默认构造函数打印“A”的值。当我们创建一个类型为 A 的对象数组时，所有对象的默认构造函数都被逐个调用。因此，我们将从 1 到 100 的所有值打印在屏幕上。

下面是使用**转到**关键字打印 1 到 100 的轻量方法，没有循环和递归。

## C++

```cpp
#include<iostream>

int main()
{
    short sum = 0;

    update: sum++ ;
    std::cout<<sum<<std::endl;

      if(sum == 100) return 0;
    goto update;
}
```

该程序的输出与上述程序相同。在上面的程序中，goto 关键字被再次跳转到名为 update 的标签。“sum”的值会在每次调用时打印并递增。一旦变量和等于 100，程序就停止执行。这样，我们可以在控制台上打印从 1 到 100 的所有值。

感谢*拉克希米南*提出这个方法。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。