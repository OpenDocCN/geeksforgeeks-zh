# 指向 Go 中某个函数的指针

> 原文:[https://www.geeksforgeeks.org/pointers-to-a-function-in-go/](https://www.geeksforgeeks.org/pointers-to-a-function-in-go/)

#### 先决条件:[Go 中的指针](https://www.geeksforgeeks.org/pointers-in-golang/)

[Go 编程语言](https://www.geeksforgeeks.org/go-programming-language-introduction/)或 Golang 中的指针是一个变量，用来存储另一个变量的内存地址。您也可以将指针传递给像[变量](https://www.geeksforgeeks.org/go-variables/)这样的函数。有两种方法可以做到这一点，如下所示:

#### 创建一个指针，并简单地将其传递给函数

在下面的程序中，我们取了一个函数 *ptf* ，它有一个整数类型指针参数，指示函数只接受指针类型参数。基本上，这个函数改变了变量 *x* 的值。开始时 *x* 包含值 100。但是在函数调用之后，值变成了 748，如输出所示。

## 去

```go
// Go program to create a pointer
// and passing it to the function
package main

import "fmt"

// taking a function with integer
// type pointer as an parameter
func ptf(a *int) {

    // dereferencing
    *a = 748
}

// Main function
func main() {

    // taking a normal variable
    var x = 100

        fmt.Printf("The value of x before function call is: %d\n", x)

    // taking a pointer variable
    // and assigning the address
    // of x to it
    var pa *int = &x

    // calling the function by
    // passing pointer to function
    ptf(pa)

    fmt.Printf("The value of x after function call is: %d\n", x)

}
```

**输出:**

```go
The value of x before function call is: 100
The value of x after function call is: 748
```

#### 将变量的地址传递给函数调用

考虑到下面的程序，我们没有创建一个指针来存储变量 *x* 的地址，即像上面程序中的 *pa* 一样。我们直接将 **x** 的地址传递给函数调用，其工作方式与上面讨论的方法类似。

## 去

```go
// Go program to create a pointer
// and passing the address of the
// variable to the function
package main

import "fmt"

// taking a function with integer
// type pointer as an parameter
func ptf(a *int) {

    // dereferencing
    *a = 748
}

// Main function
func main() {

    // taking a normal variable
    var x = 100

    fmt.Printf("The value of x before function call is: %d\n", x)

    // calling the function by
    // passing the address of
    // the variable x
    ptf(&x)

    fmt.Printf("The value of x after function call is: %d\n", x)

}
```

**输出:**

```go
The value of x before function call is: 100
The value of x after function call is: 748
```

**注意:**也可以使用短声明运算符(:=)来声明上述程序中的变量和指针。