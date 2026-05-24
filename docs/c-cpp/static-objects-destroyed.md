# 静止物体什么时候被破坏？

> 原文:[https://www.geeksforgeeks.org/static-objects-destroyed/](https://www.geeksforgeeks.org/static-objects-destroyed/)

小心这两个人
新朋友和老敌人 —卡比尔

**什么是 C++ 中的静态关键字？**
static 关键字可以应用于 C++ 中的局部变量、函数、类的数据成员和对象。静态局部变量在函数调用之间保留它们值，且只初始化一次。静态函数可以使用类名前面的作用域解析运算符直接调用(详见[本](https://www.geeksforgeeks.org/some-interesting-facts-about-static-member-functions-in-c/)、[本](https://www.geeksforgeeks.org/stati/)本)。C++ 也支持静态对象。

**c++ 中什么是静态对象？**
当一个对象的声明中使用了 static 关键字时，它就会变成静态的。参见下面两个 C++ 语句示例。

```cpp
Test t;             // Stack based object
static Test t1;     // Static object 
```

执行时的第一条语句在堆栈上创建对象意味着存储在堆栈上分配。基于堆栈的对象也称为自动对象或本地对象。静态对象只初始化一次，并一直存在到程序终止。每次在程序执行中遇到本地对象的声明时，都会创建一个本地对象。

静态对象被分配到静态存储区的存储中。静态对象在程序结束时被销毁。C++ 同时支持局部静态对象和全局静态对象
下面是展示局部静态对象使用的例子。

```cpp
#include <iostream>
class Test 
{
public:
    Test()
    {
        std::cout << "Constructor is executed\n";
    }
    ~Test()
    {
        std::cout << "Destructor is executed\n";
    }
};
void myfunc()
{
    static Test obj;
} // Object obj is still not destroyed because it is static

int main()
{
    std::cout << "main() starts\n";
    myfunc();    // Destructor will not be called here
    std::cout << "main() terminates\n";
    return 0;
}
```

输出:

```cpp
main() starts
Constructor is executed
main() terminates
Destructor is executed 
```

如果我们仔细观察这个程序的输出，我们可以看到名为 obj 的本地对象的析构函数在它的构造函数被执行后没有被调用，因为本地对象是静态的，所以它在程序的生命周期内都有作用域，所以当 main()终止时，它的析构函数将被调用。

**当我们在上面的程序中移除静态时会发生什么？**
作为一个实验，如果我们从全局函数 myfunc()中移除 static 关键字，我们得到如下输出:

```cpp
main() starts
Constructor is called
Destructor is called
main() terminates
```

这是因为该对象现在是基于堆栈的对象，当它超出范围时将被销毁，并且将调用其析构函数。

**全局静态对象怎么样？**
下面的程序演示了全局静态对象的使用。

```cpp
#include <iostream>
class Test
{
public:
    int a;
    Test()
    {
        a = 10;
        std::cout << "Constructor is executed\n";
    }
    ~Test()
    {
        std::cout << "Destructor is executed\n";
    }
};
static Test obj;
int main()
{
    std::cout << "main() starts\n";
    std::cout << obj.a;
    std::cout << "\nmain() terminates\n";
    return 0;
}
```

输出:

```cpp
Constructor is executed
main() starts
10
main() terminates
Destructor is executed
```

本文由**遇见普拉瓦西**供稿。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论