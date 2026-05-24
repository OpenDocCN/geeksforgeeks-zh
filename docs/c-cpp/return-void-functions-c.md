# 从 C++ 中的 void 函数返回

> 原文:[https://www.geeksforgeeks.org/return-void-functions-c/](https://www.geeksforgeeks.org/return-void-functions-c/)

Void 函数是“void”，因为它们不应该返回值。没错，但不完全是。我们不能返回值，但是我们肯定可以从 void 函数中返回一些东西。下面列出了一些案例。

**一个 void 函数可以做 return**
我们可以简单的在一个 void fun()中写 return 语句。事实上，编写 return 被认为是一种好的做法(为了代码的可读性)；语句来指示函数的结束。

```cpp
#include <iostream>
using namespace std;

void fun()
{
   cout << "Hello";

   // We can write return in void
   return; 
}

int main()
{
   fun();
   return 0;
}
```

输出:

```cpp
Hello
```

**一个虚空乐趣()可以返回另一个虚空功能**

```cpp
// C++ code to demonstrate void()
// returning void()
#include<iostream>
using namespace std;

// A sample void function
void work()
{
    cout << "The void function has returned "
            " a void() !!! \n";
}

// Driver void() returning void work()
void test()
{
    // Returning void function
    return work();
}

int main()
{
    // Calling void function
    test();
    return 0;
}
```

输出:

```cpp
The void function has returned a void() !!! 

```

上面的代码解释了 void()如何在不出错的情况下返回 void 函数。

**一个 void()可以返回一个 void 值。**
一个 void()不能返回一个可以使用的值。但是它可以返回一个无效的值而不会给出错误。

```cpp
// C++ code to demonstrate void()
// returning a void value
#include<iostream>
using namespace std;

// Driver void() returning a void value
void test()
{
    cout << "Hello";  

    // Returning a void value
    return (void)"Doesn't Print";
}
int main()
{  
    test();
    return 0;
}
```

输出:

```cpp
Hello

```

本文由**曼吉特·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。