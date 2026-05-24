# 在 C++ 中复制省略

> 原文:[https://www.geeksforgeeks.org/copy-elision-in-c/](https://www.geeksforgeeks.org/copy-elision-in-c/)

[复制省略](http://en.wikipedia.org/wiki/Copy_elision)(或 Copy 省略)是一种编译器优化技术，可以避免不必要的对象复制。如今，几乎每个编译器都在使用它。让我们借助一个例子来理解它。

```cpp
#include <iostream>
using namespace std;

class B
{
public:    
    B(const char* str = "\0") //default constructor
    {
        cout << "Constructor called" << endl;
    }    

    B(const B &b)  //copy constructor
    {
        cout << "Copy constructor called" << endl;
    } 
};

int main()
{ 
    B ob = "copy me"; 
    return 0;
}
```

上述程序的输出为:

```cpp
Constructor called

```

***为什么不调用复制构造函数？***
根据理论，在构造对象“ob”时，使用一个自变量构造器将“copy me”转换为临时对象&即临时对象被复制到对象“ob”。所以声明

```cpp
     B ob = "copy me"; 
```

应该被编译器分解为

```cpp
     B ob = B("copy me");
```

然而，大多数 C++ 编译器避免了创建临时对象然后复制它的开销。

```cpp
The modern compilers break down the statement
    B ob = "copy me"; //copy initialization
as
    B ob("copy me"); //direct initialization
and thus eliding call to copy constructor.

```

但是，如果我们仍然希望确保编译器不省略对复制构造函数的调用[禁用复制省略]，我们可以使用 g++ 的“-fno-elide-constructors”选项编译程序，并看到如下输出:

```cpp
  aashish@aashish-ThinkPad-SL400:~$ g++ copy_elision.cpp -fno-elide-constructors
  aashish@aashish-ThinkPad-SL400:~$ ./a.out
  Constructor called
  Copy constructor called

```

如果使用“-fno-elide-constructors”选项，首先调用默认构造函数创建临时对象，然后调用复制构造函数将临时对象复制到 ob。

**参考资料:**
[http://en . Wikipedia . org/wiki/copy _ elision](http://en.wikipedia.org/wiki/Copy_elision)

本文由**aashis Barnwal**编辑，GeeksforGeeks 团队审核。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论