# c++ 中新 vs 运算符新

> 原文:[https://www.geeksforgeeks.org/new-vs-operator-new-in-cpp/](https://www.geeksforgeeks.org/new-vs-operator-new-in-cpp/)

创建新对象时，使用运算符 new 函数分配内存，然后调用构造函数来初始化内存。这里，新的操作符执行分配和初始化，而新的操作符只执行分配。
让我们看看这两者是如何独立工作的。

**新增关键词**

新的操作符是一个**操作符**，表示对堆内存分配的请求。如果有足够的内存，new 运算符初始化内存，并将新分配和初始化的内存的地址返回给指针变量。当您使用 new 关键字(普通 new)创建类对象时。

*   使用堆中的**运算符 new** 来分配对象的内存。
*   调用类的构造函数来正确初始化这个内存。

```cpp
// CPP program to illustrate 
// use of new keyword
#include<iostream>
using namespace std;
class car
{
    string name;
    int num;

    public:
        car(string a, int n)
        {
            cout << "Constructor called" << endl;
            this ->name = a;
            this ->num = n;
        }

        void enter()
        {
            cin>>name;
            cin>>num;
        }

        void display()
        {
            cout << "Name: " << name << endl;
            cout << "Num: " << num << endl;
        }
};

int main()
{
    // Using new keyword
    car *p = new car("Honda", 2017);
    p->display();
}
```

输出:

```cpp
Constructor called
Name: Honda
Num: 2017

```

**操作员新增**

Operator new 是一个分配原始内存的**函数**，在概念上有点类似于 [malloc()](https://www.geeksforgeeks.org/malloc-vs-new/) 。

*   这是覆盖默认堆分配逻辑的机制。
*   它不初始化内存，即不调用构造函数。然而，在我们重载的新返回之后，编译器会自动调用构造函数。
*   也有可能在全球范围内或针对特定类别使新的操作员超载

```cpp
// CPP program to illustrate 
// use of operator new
#include<iostream>
#include<stdlib.h>

using namespace std;

class car
{
    string name;
    int num;

    public:

        car(string a, int n)
        {
            cout << "Constructor called" << endl;
            this->name = a;
            this->num = n;
        }

        void display()
        { 
            cout << "Name: " << name << endl;
            cout << "Num: " << num << endl;
        }

        void *operator new(size_t size)
        {
            cout << "new operator overloaded" << endl;
            void *p = malloc(size);
            return p;
        }

        void operator delete(void *ptr)
        {
            cout << "delete operator overloaded" << endl;
            free(ptr);
        }
};

int main()
{
    car *p = new car("HYUNDAI", 2012);
    p->display();
    delete p;
}
```

输出:

```cpp
new operator overloaded
Constructor called
Name:HYUNDAI
Num:2012
delete operator overloaded

```

**新操作员 vs 新操作员**

1.  **运算符 vs 函数:** new 是一个运算符，也是一个关键字，而 operator new 只是一个函数。
2.  **New 调用“Operator new”:**“New Operator”调用“Operator New()”，就像方式+ operator 调用 operator +()
3.  **“操作员新”可以重载:**操作员新可以重载，就像允许我们执行定制任务的功能一样。
4.  **内存分配:**‘new expression’调用‘operator new’分配原始内存，然后调用构造函数。

本文由**雅什辛拉**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。