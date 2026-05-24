# 我们可以在 C 和 C++ 中使用表达式左侧的函数吗？

> 原文:[https://www . geeksforgeeks . org/can-we-use-function-on-on-one-expression-in-c-and-CPP/](https://www.geeksforgeeks.org/can-we-use-function-on-left-side-of-an-expression-in-c-and-cpp/)

在 C 语言中，表达式的左侧不可能有函数名，但在 C++ 中是可能的。

**如何在 C++ 中使用一个表达式左侧的函数？**

在 C++ 中，只有返回一些引用变量的**函数可以用在表达式的左侧。引用的工作方式类似于 [**指针**](https://www.geeksforgeeks.org/pointers-in-c-and-c-set-1-introduction-arithmetic-and-array/) ，因此每当函数返回引用时，隐式指针都会返回到其返回值。因此，通过这个，我们可以在赋值语句的左侧使用一个函数。上面已经用下面给出的例子进行了说明，**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate using a function on left side
// of an expression in C++
#include <iostream>
using namespace std;

// such a function will not be safe if x is non static
// variable of it
int& fun()
{
    static int x;
    return x;
}

// Driver Code
int main()
{
    fun() = 10;

    // this line prints 10 as output
    printf(" %d ", fun());

    getchar();
    return 0;
}
```

**Output**

```cpp
 10 
```