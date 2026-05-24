# c++ 中的抽象

> 原文:[https://www.geeksforgeeks.org/abstraction-in-c/](https://www.geeksforgeeks.org/abstraction-in-c/)

数据抽象是 C++ 中面向对象编程最本质、最重要的特征之一。抽象意味着只显示基本信息，隐藏细节。数据抽象是指只向外界提供数据的基本信息，隐藏背景细节或实现。

考虑一个男人开车的真实例子。这个人只知道踩油门会提高汽车的速度，或者踩刹车会让汽车停下来，但他不知道踩油门后速度实际上是如何提高的，他不知道汽车的内部机制或者油门、刹车等在汽车中的实施。这就是抽象。
 **使用类的抽象:**我们可以使用类在 C++ 中实现抽象。类帮助我们使用可用的访问说明符对数据成员和成员函数进行分组。类可以决定哪个数据成员对外部世界可见，哪个不可见。

**头文件中的抽象:**c++ 中还有一种抽象类型可以是头文件。例如，考虑 math.h 头文件中的 pow()方法。每当我们需要计算一个数的幂时，我们只需调用 math.h 头文件中的函数 pow()，并将这些数作为参数传递，而不知道函数实际上是根据什么算法计算数的幂的。

**使用访问说明符的抽象**

访问说明符是在 C++ 中实现抽象的主要支柱。我们可以使用访问说明符来强制限制类成员。例如:

*   在一个类中声明为**公共**的成员，可以从程序中的任何地方访问。
*   在一个类中声明为**私有**的成员只能从该类中访问。不允许从类外的任何代码部分访问它们。

我们可以使用访问说明符提供的上述两个特性轻松实现抽象。比方说，定义内部实现的成员可以在类中标记为私有。而需要对外提供的重要信息可以标注为公开。这些公共成员可以像在类中一样访问私有成员。

**例**:

```cpp
#include <iostream>
using namespace std;

class implementAbstraction
{
    private:
        int a, b;

    public:

        // method to set values of 
        // private members
        void set(int x, int y)
        {
            a = x;
            b = y;
        }

        void display()
        {
            cout<<"a = " <<a << endl;
            cout<<"b = " << b << endl;
        }
};

int main() 
{
    implementAbstraction obj;
    obj.set(10, 20);
    obj.display();
    return 0;
}
```

输出:

```cpp
a = 10
b = 20

```

你可以看到在上面的程序中，我们不允许直接访问变量 a 和 b，但是我们可以调用函数 set()来设置 a 和 b 中的值，调用函数 display()来显示 a 和 b 的值。

**数据抽象的优势**:

*   帮助用户避免编写低级代码
*   避免代码重复并提高可重用性。
*   可以在不影响用户的情况下独立更改类的内部实现。
*   有助于提高应用程序或程序的安全性，因为只有重要的细节才提供给用户。

本文由 [**哈什·阿加瓦尔**](https://www.facebook.com/harsh.agarwal.16752) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。