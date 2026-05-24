# int * p()和 int (*p)()的区别？

> 原文:[https://www . geesforgeks . org/difference-int-p 和-int-p/](https://www.geeksforgeeks.org/difference-between-int-p-and-int-p/)

A [**指针**](https://www.geeksforgeeks.org/pointers-in-c-and-c-set-1-introduction-arithmetic-and-array/) 是一个变量，其值是另一个变量的地址，即内存位置的直接地址。像任何[变量或常量](https://www.geeksforgeeks.org/different-ways-declare-variable-constant-c-c/)一样，指针必须在存储任何变量地址之前声明。指针变量声明的一般形式是:

**语法:**

```cpp
type *var_name;
```

这里，**类型**是指针的基本类型。必须是有效的 [C](https://www.geeksforgeeks.org/c/) / [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) [数据类型](https://www.geeksforgeeks.org/c-data-types/)， **var-name** 是指针变量的名称。**星号*** 用于将变量指定为指针。以下是它们各自数据类型的有效指针声明:

```cpp
int *ip;
float *fp;
double *dp;
char *cp;

```

本文的重点是区分 **int* p()** 和**int(* p()(**)。

**int* p()** :这里**“p”**是一个没有参数的函数，返回一个整数指针。

```cpp
int* p()
returntype function_name (arguments)
```

下面是说明 **int* p()** 用法的程序:

## C++

```cpp
// C++ program to demonstrate the use
// of int* p()
#include <bits/stdc++.h>
using namespace std;

// Function that returns integer pointer
// and no arguments
int* p()
{
    int a = 6, b = 3;
    int c = a + b;
    int* t = &c;
    return t;
}

// Driver Code
int main()
{
    // Declare pointer a
    int* a = p();
    cout << *a;
}
```

**Output:**

```cpp
9

```

**int(* p)(:**)这里的“p”是一个[函数指针](https://www.geeksforgeeks.org/function-pointer-in-c/)，它可以存储一个不带参数并返回整数的函数的地址。 ***p** 是功能， **p** 是指针。

下面是说明**int(* p)(**)用法的程序:

## C++

```cpp
// C++ program to demonstrate the use
// of int* (*p)()
#include <bits/stdc++.h>
using namespace std;

// Function with no arguments
// and return integer
int gfg()
{
    int a = 5, b = 9;
    return a + b;
}

// Driver Code
int main()
{
    // Declaring Function Pointer
    int (*p)();

    // Storing the address of
    // function gfg in function
    // pointer
    p = gfg;

    // Invoking function using
    // function pointer
    cout << p() << endl;
}
```

**Output:**

```cpp
14

```