# c++ 中的命名空间|集合 1(简介)

> 原文:[https://www.geeksforgeeks.org/namespace-in-c/](https://www.geeksforgeeks.org/namespace-in-c/)

考虑遵循 C++ 程序。

```cpp
// A program to demonstrate need of namespace
int main()
{
    int value;
    value = 0;
    double value; // Error here
    value = 0.0;
}
```

输出:

```cpp
Compiler Error:
'value' has a previous declaration as 'int value'
```

在每个作用域中，一个名称只能代表一个实体。所以，在同一个作用域中不能有两个同名的变量。使用名称空间，我们可以创建两个同名的变量或成员函数。

```cpp
// Here we can see that more than one variables 
// are being used without reporting any error.
// That is because they are declared in the 
// different namespaces and scopes.
#include <iostream>
using namespace std;

// Variable created inside namespace
namespace first
{
    int val = 500;
}

// Global variable
int val = 100;

int main()
{
    // Local variable
    int val = 200;

    // These variables can be accessed from
    // outside the namespace using the scope
    // operator ::
    cout << first::val << '\n'; 

    return 0;
}
```

**输出:**

```cpp
500
```

<center>**Definition and Creation:**</center>

Namespaces allow us to group named entities that otherwise would have *global scope* into narrower scopes, giving them *namespace scope*. This allows organizing the elements of programs into different logical scopes referred to by names.

*   命名空间是在 C++ 中添加的特性，在 C 中不存在。
*   命名空间是一个声明性区域，它为其中的标识符(类型、函数、变量等的名称)提供了一个范围。
*   允许多个名称相同的命名空间块。这些块中的所有声明都在命名范围中声明。

命名空间定义以关键字**命名空间**开始，然后是命名空间名称，如下所示:

```cpp
namespace namespace_name 
{
   int x, y; // code declarations where 
             // x and y are declared in 
             // namespace_name's scope
}

```

*   命名空间声明只出现在全局范围内。
*   命名空间声明可以嵌套在另一个命名空间中。
*   命名空间声明没有访问说明符。(公共或私人)
*   不需要在名称空间定义的右大括号后给出分号。
*   我们可以将命名空间的定义分成几个单元。

```cpp
// Creating namespaces
#include <iostream>
using namespace std;
namespace ns1
{
    int value()    { return 5; }
}
namespace ns2 
{
    const double x = 100;
    double value() {  return 2*x; }
}

int main()
{
    // Access value function within ns1
    cout << ns1::value() << '\n'; 

    // Access value function within ns2
    cout << ns2::value() << '\n'; 

    // Access variable x directly
    cout << ns2::x << '\n';       

    return 0;
}
```

**输出:**

```cpp
5
200
100
```

<center>**Classes and Namespace:**</center>

Following is a simple way to create classes in a name space

```cpp
// A C++ program to demonstrate use of class
// in a namespace
#include <iostream>
using namespace std;

namespace ns
{
    // A Class in a namespace
    class geek
    {
    public:
        void display()
        {
            cout << "ns::geek::display()\n";
        }
    };
}

int main()
{
    // Creating Object of geek Class
    ns::geek obj;

    obj.display();

    return 0;
}
```

输出:

```cpp
ns::geek::display()
```

**类也可以在命名空间内部声明，并使用以下语法在命名空间外部定义**

```cpp
// A C++ program to demonstrate use of class
// in a namespace
#include <iostream>
using namespace std;

namespace ns
{
    // Only declaring class here
    class geek;
}

// Defining class outside
class ns::geek
{
public:
    void display()
    {
        cout << "ns::geek::display()\n";
    }
};

int main()
{
    //Creating Object of geek Class
    ns::geek obj;
    obj.display();
    return 0;
}
```

输出:

```cpp
ns::geek::display()
```

我们也可以在命名空间之外定义方法。下面是一个示例代码。

```cpp
// A C++ code to demonstrate that we can define 
// methods outside namespace.
#include <iostream>
using namespace std;

// Creating a namespace
namespace ns
{
    void display();
    class geek
    {
    public:
       void display();
    };
}

// Defining methods of namespace
void ns::geek::display()
{
    cout << "ns::geek::display()\n";
}
void ns::display()
{
    cout << "ns::display()\n";
}

// Driver code
int main()
{
    ns::geek obj;
    ns::display();
    obj.display();
    return 0;
}
```

**输出:**

```cpp
ns::display()
ns::geek::display()
```

[C++ 中的命名空间|集合 2(扩展命名空间和未命名的命名空间)](https://www.geeksforgeeks.org/namespace-in-c-set-2-extending-namespace-and-unnamed-namespace/)
[c++ 中的命名空间|集合 3(访问、创建头、嵌套和别名)](https://www.geeksforgeeks.org/namespace-c-set-3-creating-header-nesting-aliasing-accessing/)
[命名空间可以在 c++ 中嵌套吗？](https://www.geeksforgeeks.org/g-fact-62/)

**参考**:
T3】http://www.cplusplus.com/doc/tutorial/namespaces/

本文由**阿比纳夫·蒂瓦里**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论