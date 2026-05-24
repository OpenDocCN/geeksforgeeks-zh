# C/c++

中的断言

> 原文:[https://www.geeksforgeeks.org/assertions-cc/](https://www.geeksforgeeks.org/assertions-cc/)

断言是用于测试程序员所做假设的语句。例如，我们可以使用断言来检查 malloc()返回的指针是否为空。
以下是断言的语法。

```cpp
void assert( int expression ); 
```

如果表达式的计算结果为 0 (false)，则将表达式、源代码文件名和行号发送到标准错误，然后调用 abort()函数。
例如，考虑以下程序。

## C

```cpp
#include <stdio.h>
#include <assert.h>

int main()
{
    int x = 7;

    /*  Some big code in between and let's say x
       is accidentally changed to 9  */
    x = 9;

    // Programmer assumes x to be 7 in rest of the code
    assert(x==7);

    /* Rest of the code */

    return 0;
}
```

输出

```cpp
Assertion failed: x==7, file test.cpp, line 13 
This application has requested the Runtime to terminate it in an unusual 
way. Please contact the application's support team for more information.
```

**断言 Vs 正常错误处理**
断言主要用于检查逻辑上不可能的情况。例如，它们可以用来检查代码在开始运行前的预期状态或在结束运行后的状态。与正常的错误处理不同，断言通常在运行时被禁用。因此，在 assert()中编写可能导致副作用的语句并不是一个好主意。例如，编写像 assert(x = 5)这样的东西不是一个好主意，因为 x 被改变了，并且当断言被禁用时，这种改变不会发生。详见[本](https://www.geeksforgeeks.org/understanding-exit-abort-and-assert/)。
**忽略断言**
在 C/C++ 中，我们可以使用预处理器 NDEBUG 在编译时完全移除断言。

## C

```cpp
// The below program runs fine because NDEBUG is defined
# define NDEBUG
# include <assert.h>

int main()
{
    int x = 7;
    assert (x==5);
    return 0;
}
```

以上程序编译运行良好。
在 Java 中，断言默认情况下是不被启用的，我们必须向运行时引擎传递一个选项来启用它们。
**参考:**
[http://en . Wikipedia . org/wiki/Assertion _ % 28 software _ development % 29](http://en.wikipedia.org/wiki/Assertion_%28software_development%29)
如发现有不正确的地方，或想分享更多关于上述话题的信息，请写评论。