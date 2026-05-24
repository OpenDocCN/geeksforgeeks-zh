# Golang 中的函数参数

> 原文:[https://www.geeksforgeeks.org/function-arguments-in-golang/](https://www.geeksforgeeks.org/function-arguments-in-golang/)

Golang 中的一个[函数](https://www.geeksforgeeks.org/functions-in-go-language/)是一组语句的集合，用于执行特定的任务并将结果返回给调用者。一个函数也可以在不返回任何东西的情况下执行一些特定的任务。Golang 支持两种向函数传递参数的不同方式，即*按值传递或按值调用*和*按引用传递或按引用调用*。默认情况下，Golang 使用按值调用的方式将参数传递给函数。

**传递给函数的参数中的基本术语:**

*   传递给函数的参数称为实际参数。
*   函数接收的参数称为形式参数。

### 按值调用

在这个参数传递中，实际参数的值被复制到函数的形式参数中，这两种类型的参数被存储在不同的内存位置。因此，函数内部所做的任何更改都不会反映在调用者的实际参数中。

**例 1:** 在下面的程序中，可以看到 Z 的值是不能被*修改*功能修改的。

```go
// Go program to illustrate the
// concept of the call by value
package main

import "fmt"

// function which modifies
// the value
func modify(Z int) {
    Z = 70
}

// Main function
func main() {

    var Z int = 10

    fmt.Printf("Before Function Call, value of Z is = %d", Z)

    // call by value
    modify(Z)

    fmt.Printf("\nAfter Function Call, value of Z is = %d", Z)
}
```

**输出:**

```go
Before Function Call, value of Z is = 10
After Function Call, value of Z is = 10

```

**示例 2:** 在下面的程序中，交换函数无法交换值，因为我们正在使用按值调用。

```go
// Go program to illustrate the
// concept of the call by value
package main

import "fmt"

// function which swap values
func swap(x, y int) int {

    // taking a temporary variable
    var tmp int

    tmp = x
    x = y
    y = tmp

    return tmp
}

// Main function
func main() {

    var f int = 700
    var s int = 900

    fmt.Printf("Values Before Function Call\n")
    fmt.Printf("f = %d and s = %d\n", f, s)

    // call by values
    swap(f, s)

    fmt.Printf("\nValues After Function Call\n")
    fmt.Printf("f = %d and s = %d", f, s)
}
```

**输出:**

```go
Values Before Function Call
f = 700 and s = 900

Values After Function Call
f = 700 and s = 900

```

### 引用调用

在这里，您将使用[指针](https://www.geeksforgeeks.org/pointers-in-golang/)的概念。取消引用运算符*用于访问地址中的值。地址运算符&用于获取任何数据类型的变量的地址。实际参数和形式参数都引用相同的位置，因此函数内部所做的任何更改实际上都反映在调用方的实际参数中。

**示例 1:** 在函数调用中，我们传递变量的地址，并使用解引用运算符*来修改值。所以在功能即*修改*后，你会发现更新后的值。

```go
// Go program to illustrate the
// concept of the call by Reference
package main

import "fmt"

// function which modifies
// the value
func modify(Z *int) {
    *Z = 70
}

// Main function
func main() {

    var Z int = 10

    fmt.Printf("Before Function Call, value of Z is = %d", Z)

    // call by Reference
    // by passing the address
    // of the variable Z
    modify(&Z)

    fmt.Printf("\nAfter Function Call, value of Z is = %d", Z)
}
```

**输出:**

```go
Before Function Call, value of Z is = 10
After Function Call, value of Z is = 70

```

**示例 2:** 通过使用引用调用，交换函数将能够交换如下所示的值。

```go
// Go program to illustrate the
// concept of the call by Reference
package main

import "fmt"

// function which swap values
// taking the pointer to integer
func swap(x, y *int) int {

    // taking a temporary variable
    var tmp int

    tmp = *x
    *x = *y
    *y = tmp

    return tmp
}

// Main function
func main() {

    var f int = 700
    var s int = 900

    fmt.Printf("Values Before Function Call\n")
    fmt.Printf("f = %d and s = %d\n", f, s)

    // call by Reference
    // by passing the address 
    // of the variables
    swap(&f, &s)

    fmt.Printf("\nValues After Function Call\n")
    fmt.Printf("f = %d and s = %d", f, s)
}
```

**输出:**

```go
Values Before Function Call
f = 700 and s = 900

Values After Function Call
f = 900 and s = 700

```