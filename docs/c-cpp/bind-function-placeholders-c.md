# 在 C++ 中绑定函数和占位符

> 原文:[https://www.geeksforgeeks.org/bind-function-placeholders-c/](https://www.geeksforgeeks.org/bind-function-placeholders-c/)

有时我们需要根据需要操纵函数的操作，例如将一些参数更改为默认值等。预先定义一个函数有[默认参数](https://www.geeksforgeeks.org/default-arguments-c/)限制了函数的通用性，迫使我们每次都使用类似值的默认参数。从 C++ 11 开始，bind 函数的引入使得这个任务变得更加容易。

【bind()是如何工作的？
借助占位符绑定函数，有助于操作函数要使用的值的位置和数量，并根据所需的输出修改函数。

**什么是占位符？**
占位符是命名空间，用于指示函数中值的位置。他们由 **_1、_2、_3** 代表…

```cpp
// C++ code to demonstrate bind() and
// placeholders
#include <iostream>
#include <functional> // for bind()
using namespace std;

// for placeholders
using namespace std::placeholders;

// Driver function to demonstrate bind()
void func(int a, int b, int c)
{
    cout << (a - b - c) << endl;
}

int main()
{
    // for placeholders
    using namespace std::placeholders;

    // Use of bind() to bind the function
    // _1 is for first parameter and assigned
    // to 'a' in above declaration.
    // 2 is assigned to b
    // 3 is assigned to c
    auto fn1 =  bind(func, _1, 2, 3);

    // 2 is assigned to a.
    // _1 is for first parameter and assigned
    // to 'b' in above declaration.
    // 3 is assigned to c.
    auto fn2 =  bind(func, 2, _1, 3);

    // calling of modified functions
    fn1(10);
    fn2(10);

    return 0;
}
```

输出:

```cpp
5
-11

```

在上面的代码中，bind()修改了一个函数的调用，采用了 1 个参数，并返回了所需的输出。

**占位符的属性**

**1。占位符的位置决定了函数调用语句**中的值位置

```cpp
// C++ code to demonstrate placeholder
// property 1
#include <iostream>
#include <functional> // for bind()
using namespace std;

// for placeholders
using namespace std::placeholders;

// Driver function to demonstrate bind()
void func(int a, int b, int c)
{
    cout << (a - b - c) << endl;
}

int main ()
{
    // for placeholders
    using namespace std::placeholders;

    // Second parameter to fn1() is assigned
    // to 'a' in fun().
    // 2 is assigned to 'b' in fun
    // First parameter to fn1() is assigned
    // to 'c' in fun().
    auto fn1 =  bind(func, _2, 2, _1);

    // calling of function
    cout << "The value of function is : ";
    fn1(1, 13);

    // First parameter to fn2() is assigned
    // to 'a' in fun().
    // 2 is assigned to 'b' in fun
    // Second parameter to fn2() is assigned
    // to 'c' in fun().
    auto fn2 =  bind(func, _1, 2, _2);

    // calling of same function
    cout << "The value of function after changing"
         " placeholder position is : ";
    fn2(1, 13);

    return 0;
}
```

输出:

```cpp
The value of function is : 10
The value of function after changing placeholder position is : -14

```

在上面的代码中，即使 1 和 13 在函数调用中的位置相同，占位符位置的变化也改变了函数的调用方式。

**2。占位符的数量决定了传入函数**
所需的参数数量。我们可以在函数调用语句中使用任意数量的占位符(明显少于最大参数数量)。其余值由用户定义的默认值替换。

```cpp
// C++ code to demonstrate placeholder 
// property 2
#include <iostream>     
#include <functional> // for bind()
using namespace std;

// for placeholders
using namespace std::placeholders; 

// Driver function to demonstrate bind()
void func(int a,int b, int c)
{   
    cout << (a - b - c) << endl;
}

int main() 
{
    // for placeholders
    using namespace std::placeholders;

    // 1 placeholder  
    auto fn1 =  bind(func, _1, 2, 4);

    // calling of function with 1 argument
    cout << "The value of function with 1 "
             "placeholder is : ";
    fn1(10);

    // 2 placeholders 
    auto fn2 =  bind(func,_1,2,_2);

    // calling of function with 2 arguments
    cout << "The value of function with 2"
            " placeholders is : ";
    fn2(13, 1);

    // 3 placeholders 
    auto fn3 =  bind(func,_1, _3, _2);

    // calling of function with 3 arguments
    cout << "The value of function with 3 "
            "placeholders is : ";
    fn3(13, 1, 4);

    return 0;  
}
```

输出:

```cpp
The value of function with 1 placeholder is : 4
The value of function with 2 placeholders is : 10
The value of function with 3 placeholders is : 8

```

在上面的代码中，占位符的数量显然等于调用函数所需的参数数量。函数的绑定是由占位符的数量和位置决定的。

本文由**曼吉特·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。