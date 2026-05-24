# 从 Go 中的函数返回指针

> 原文:[https://www . geesforgeks . org/go 中函数返回指针/](https://www.geeksforgeeks.org/returning-pointer-from-a-function-in-go/)

**先决条件:**[Go 中的指针](https://www.geeksforgeeks.org/pointers-in-golang/)和[将指针传递给函数](https://www.geeksforgeeks.org/pointers-to-a-function-in-go/)

Go 编程语言或 Golang 中的指针是一个变量，用于存储另一个变量的内存地址。我们可以传递指向函数的指针，也可以从 Golang 中的函数返回指针。在 [C](https://www.geeksforgeeks.org/c-programming-language/) / [C++](https://www.geeksforgeeks.org/c-plus-plus/) 中，不建议返回函数外局部变量的地址，因为函数返回后会超出范围。因此，要在 C/C++中执行从函数返回指针的概念，必须将局部变量定义为静态变量。

**示例:**在下面的程序中，代码行(*int LV = n1 * n1；*)将给出警告，因为它是该功能的本地。为避免警告，将其设为静态。

```go
// C++ program to return the
// pointer from a function
#include <iostream>
using namespace std;

// taking a function having
// pointer as return type
int* rpf(int);

int main()
{

    int n = 745;

    // displaying the value of n
    cout << n << endl;

    // calling the function
    cout << *rpf(n) << endl;
}

// defining function
int* rpf(int n1)
{

    // taking a local variable
    // inside the function
    int lv = n1 * n1;

    // remove comment or make the above
    // declaration as static which
    // result into successful
    // compilation
    // static int lv = n1 * n1;

    // this will give warning as we
    // are returning the address of
    // the local variable
    return &lv;
}
```

**警告**

> prog.cpp: In 函数' int * rpf(int)':
> Prog . CPP:24:9:警告:局部变量' lv '的地址返回[-wre turn-local-addr]
> int LV = n1 * n1；

**输出:**

```go
745

```

这种情况背后的主要原因是编译器总是为函数调用生成堆栈。一旦函数退出，函数堆栈也会被移除，这导致函数的局部变量超出范围。使其静态化将解决问题。因为静态变量有一个属性，即使超出了它们的范围，也能保持它们的值。

但是 **Go 编译器非常智能！**。它不会将堆栈上的内存分配给函数的局部变量。它将在堆上分配这个变量。在下面的程序中，变量 *lv* 将在堆上分配内存，因为 Go 编译器将执行转义分析以从本地范围转义该变量。

**示例:**

```go
// Go program to return the
// pointer from the function
package main

import "fmt"

// main function
func main() {

    // calling the function
    n := rpf()

    // displaying the value
    fmt.Println("Value of n is: ", *n)

}

// defining function having integer
// pointer as return type
func rpf() *int {

    // taking a local variable
    // inside the function
    // using short declaration
    // operator
    lv := 100

    // returning the address of lv
    return &lv
}
```

**输出:**

```go
Value of n is:  100

```

**注意:** Golang 不像 C/C++那样对指针算法提供任何支持。如果你要执行，那么编译器会抛出一个错误作为无效操作。