# c++ 中通过指针传递与通过引用传递

> 原文:[https://www . geesforgeks . org/按指针传递 vs 按引用传递 in-c/](https://www.geeksforgeeks.org/passing-by-pointer-vs-passing-by-reference-in-c/)

在 C++ 中，我们可以通过指针或引用将参数传递给函数。在这两种情况下，我们得到相同的结果。所以下面的问题是不可避免的；什么时候一个比另一个更受欢迎？我们用一个代替另一个的原因是什么？
**路过指针:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to swap two numbers using
// pass by pointer.
#include <iostream>
using namespace std;

void swap(int* x, int* y)
{
    int z = *x;
    *x = *y;
    *y = z;
}

int main()
{
    int a = 45, b = 35;
    cout << "Before Swap\n";
    cout << "a = " << a << " b = " << b << "\n";

    swap(&a, &b);

    cout << "After Swap with pass by pointer\n";
    cout << "a = " << a << " b = " << b << "\n";
}
```

输出:

```cpp
Before Swap
a = 45 b = 35
After Swap with pass by pointer
a = 35 b = 45
```

**路过参考:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to swap two numbers using
// pass by reference.

#include <iostream>
using namespace std;
void swap(int& x, int& y)
{
    int z = x;
    x = y;
    y = z;
}

int main()
{
    int a = 45, b = 35;
    cout << "Before Swap\n";
    cout << "a = " << a << " b = " << b << "\n";

    swap(a, b);

    cout << "After Swap with pass by reference\n";
    cout << "a = " << a << " b = " << b << "\n";
}
```

输出:

```cpp
Before Swap
a = 45 b = 35
After Swap with pass by reference
a = 35 b = 45
```

**引用变量和指针变量的区别**
引用是同一个对象，只是用不同的名字和引用必须引用一个对象。因为引用不能为空，所以使用它们更安全。

1.  指针可以重新分配，而引用不能，并且只能在初始化时分配。

2.  指针可以直接赋值为空，而引用不能。
3.  指针可以在数组上迭代，我们可以使用递增/递减操作符来转到指针所指向的下一个/上一个项目。

4.  指针是保存内存地址的变量。引用与它引用的项目具有相同的内存地址。
5.  指向类/结构的指针使用“->”(箭头运算符)来访问其成员，而引用使用“.”(点运算符)
6.  指针需要用*取消引用才能访问它所指向的内存位置，而引用可以直接使用。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate differences between pointer
// and reference.
#include <iostream>
using namespace std;

struct demo
{
    int a;
};

int main()
{
    int x = 5;
    int y = 6;
    demo d;

    int *p;
    p =  &x;
    p = &y;                     // 1\. Pointer reintialization allowed
    int &r = x;
    // &r = y;                  // 1\. Compile Error
    r = y;                      // 1\. x value becomes 6

    p = NULL;          
    // &r = NULL;               // 2\. Compile Error

    p++ ;                        // 3\. Points to next memory location
    r++ ;                        // 3\. x values becomes 7

    cout << &p << " " << &x << endl;    // 4\. Different address
    cout << &r << " " << &x << endl;    // 4\. Same address

    demo *q = &d;
    demo &qq = d;

    q->a = 8;
    // q.a = 8;                 // 5\. Compile Error
    qq.a = 8;
    // qq->a = 8;               // 5\. Compile Error

    cout << p << endl;        // 6\. Prints the address
    cout << r << endl;        // 6\. Print the value of x   

    return 0;
}
```

输出(当我们在程序中打印地址时，在不同的运行中可能不同):

```cpp
0x7ffd09172c20 0x7ffd09172c18
0x7ffd09172c18 0x7ffd09172c18
0x4
7
```

**参数传递中的用法:**
每当我们不需要“重新定位”时，引用通常比指针更受欢迎。
总的来说，**可以的时候使用引用，必须的时候使用指针**。但是，如果我们想编写同时用 C 和 C++ 编译器编译的 C 代码，您将不得不限制自己使用指针。
本文由**罗希特·卡斯勒**供稿。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。