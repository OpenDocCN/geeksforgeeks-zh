# c++ 中的构造函数重载

> 原文:[https://www.geeksforgeeks.org/constructor-overloading-c/](https://www.geeksforgeeks.org/constructor-overloading-c/)

**先决条件:**[C++ 中的构造函数](https://www.geeksforgeeks.org/constructors-c/)
在 c++ 中，我们可以在一个同名的类中有多个构造函数，只要每个构造函数都有不同的参数列表。这个概念被称为构造函数重载，与[函数重载](https://www.geeksforgeeks.org/function-overloading-c/)非常相似。

*   重载构造函数本质上具有相同的名称(类的确切名称)，并且参数的数量和类型不同。
*   根据传递的参数的数量和类型调用构造函数。
*   创建对象时，必须传递参数让编译器知道需要调用哪个构造函数。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate
// Constructor overloading
#include <iostream>
using namespace std;

class construct
{

public:
    float area;

    // Constructor with no parameters
    construct()
    {
        area = 0;
    }

    // Constructor with two parameters
    construct(int a, int b)
    {
        area = a * b;
    }

    void disp()
    {
        cout<< area<< endl;
    }
};

int main()
{
    // Constructor Overloading
    // with two different constructors
    // of class name
    construct o;
    construct o2( 10, 20);

    o.disp();
    o2.disp();
    return 1;
}
```

输出:

```cpp
0
200

```

**相关文章:**

*   [c++ 中的析构函数](https://www.geeksforgeeks.org/destructors-c/)
*   [c++ 中构造函数的测试](https://www.geeksforgeeks.org/c-plus-plus-gq/constructors-gq/)
*   [c++ 程序输出|集合 26(构造函数)](https://www.geeksforgeeks.org/output-c-programs-set-26-constructors/)
*   [c++ 程序输出|集合 27(构造函数和析构函数)](https://www.geeksforgeeks.org/output-c-programs-set-27-constructors-destructors/)

本文由 [I.HARISH KUMAR](https://www.facebook.com/harishkumar.injamuri) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。