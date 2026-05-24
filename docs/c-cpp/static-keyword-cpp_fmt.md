# C++ 中的静态关键字

> 原文: [https://www.geeksforgeeks.org/static-keyword-cpp/](https://www.geeksforgeeks.org/static-keyword-cpp/)

先决条件: [C 中的静态变量](https://www.geeksforgeeks.org/static-variables-in-c/)

`static` 关键字在与不同类型一起使用时有不同的含义。我们可以使用 `static` 关键字:

- **静态变量:** 函数中的变量，类中的变量
- **类的静态成员:** 类中的对象和函数

现在让我们详细看看 `static` 的每一种用法:

## 静态变量

### Static variables in a Function

当一个变量被声明为 `static` 时，**它获得的空间分配会持续到程序生命周期结束**。即使函数被多次调用，静态变量的空间也只分配一次，并且变量在前一次调用中的值会被带到下一次函数调用。这对于实现 [C/C++ 中的协程](https://www.geeksforgeeks.org/coroutines-in-c-cpp/) 或任何其他需要存储函数先前状态的应用非常有用。

```cpp
// C++ program to demonstrate 
// the use of static Static 
// variables in a Function
#include <iostream>
#include <string>
using namespace std;

void demo()
{ 
    // static variable
    static int count = 0;
    cout << count << " ";

    // value is updated and
    // will be carried to next
    // function calls
    count++ ;
}

int main()
{
    for (int i=0; i<5; i++)    
        demo();
    return 0;
}
```

输出:

```
0 1 2 3 4
```

您可以在上面的程序中看到变量 `count` 被声明为静态的。所以，它的值是通过函数调用传递的。每次调用函数时，变量 `count` 都不会初始化。
顺便提一下， [Java 不允许函数](https://www.geeksforgeeks.org/g-fact-47/)中有静态局部变量。

### Static variables in a class

由于被声明为 `static` 的变量只初始化一次，因为它们被分配在单独的静态存储区中，所以**类中的静态变量是被所有对象共享的**。不同对象不能有相同静态变量的多个副本。也因为这个原因，静态变量不能使用构造函数来初始化。

```cpp
// C++ program to demonstrate static
// variables inside a class

#include<iostream>
using namespace std;

class GfG
{
   public:
     static int i;

     GfG()
     {
        // Do nothing
     };
};

int main()
{
  GfG obj1;
  GfG obj2;
  obj1.i =2;
  obj2.i = 3;

  // prints value of i
  cout << obj1.i<<" "<<obj2.i;   
}
```

您可以在上面的程序中看到，我们试图为多个对象创建静态变量 `i` 的多个副本。但这并没有发生。因此，类内的静态变量应该由用户使用类名和作用域解析运算符在类外显式初始化，如下所示:

```cpp
// C++ program to demonstrate static
// variables inside a class

#include<iostream>
using namespace std;

class GfG
{
public:
    static int i;

    GfG()
    {
        // Do nothing
    };
};

int GfG::i = 1;

int main()
{
    GfG obj;
    // prints value of i
    cout << obj.i; 
}
```

输出:

```
1
```

## 类的静态成员

### Class objects as static

就像变量一样，对象在被声明为 `static` 时，其作用域也会持续到程序生命周期结束。
考虑下面的程序，其中对象是非静态的。

```cpp
// CPP program to illustrate
// when not using static keyword
#include<iostream>
using namespace std;

class GfG
{
    int i;
    public:
        GfG()
        {
            i = 0;
            cout << "Inside Constructor\n";
        }
        ~GfG()
        {
            cout << "Inside Destructor\n";
        }
};

int main()
{
    int x = 0;
    if (x==0)
    {
        GfG obj;
    }
    cout << "End of main\n";
}
```

输出:

```
Inside Constructor
Inside Destructor
End of main
```

在上面的程序中，对象在 `if` 块中声明为非静态的。因此，变量的作用域只在 `if` 块中。因此，当对象被创建时，构造函数被调用，并且一旦控制离开 `if` 块，析构函数就被调用，因为对象的作用域在 `if` 块内，只是在它被声明的地方。
现在让我们看看如果我们将对象声明为静态的，输出的变化。

```cpp
// CPP program to illustrate
// class objects as static
#include<iostream>
using namespace std;

class GfG
{
    int i = 0;

public:
    GfG()
    {
        i = 0;
        cout << "Inside Constructor\n";
    }

    ~GfG()
    {
        cout << "Inside Destructor\n";
    }
};

int main()
{
    int x = 0;
    if (x==0)
    {
        static GfG obj;
    }
    cout << "End of main\n";
}
```

输出:

```
Inside Constructor
End of main
Inside Destructor
```

你可以清楚地看到输出的变化。现在析构函数在 `main` 结束后被调用。这是因为静态对象的作用域贯穿了程序的生命周期。

### Static functions in a class

就像类中的静态数据成员或静态变量一样，静态成员函数也不依赖于类的对象。我们允许使用对象和 `.` 运算符来调用静态成员函数，但建议使用类名和作用域解析运算符来调用静态成员。
**静态成员函数只允许访问静态数据成员或其他静态成员函数**，它们不能访问类的非静态数据成员或成员函数。

```cpp
// C++ program to demonstrate static
// member function in a class
#include<iostream>
using namespace std;

class GfG
{
   public:

    // static member function
    static void printMsg()
    {
        cout<<"Welcome to GfG!";
    }
};

// main function
int main()
{
    // invoking a static member function
    GfG::printMsg();
}
```

输出:

```
Welcome to GfG!
```

## 相关文章

- [静态关键词测验](https://www.geeksforgeeks.org/c-plus-plus-gq/static-keyword-gq/)
- [C++ 中的静态数据成员](https://www.geeksforgeeks.org/static-data-members-cpp/)
- [静态物体什么时候被破坏？](https://www.geeksforgeeks.org/static-objects-destroyed/)
- [关于静态成员函数的有趣事实](https://www.geeksforgeeks.org/some-interesting-facts-about-static-member-functions-in-c/)
- [静态函数可以是虚函数吗？](https://www.geeksforgeeks.org/g-fact-29/)
- [C++ 和 Java 中静态关键字的比较](https://www.geeksforgeeks.org/static-keyword-in-java/)
- [C 中的静态功能](https://www.geeksforgeeks.org/what-are-static-functions-in-c/)

本文由 **Harsh Agarwal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。