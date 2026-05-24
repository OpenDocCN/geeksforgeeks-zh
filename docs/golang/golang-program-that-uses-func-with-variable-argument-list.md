# 使用带变量参数列表的 func 的 Golang 程序

> 原文:[https://www . geeksforgeeks . org/golang-使用可变参数列表的程序/](https://www.geeksforgeeks.org/golang-program-that-uses-func-with-variable-argument-list/)

在 Golang 中，可以用变量参数列表调用的函数称为[变量函数](https://www.geeksforgeeks.org/variadic-functions-in-go/)。在变量函数中可以传递零个或多个参数。如果函数定义的最后一个参数以省略号…作为前缀，那么函数可以接受该参数的任意数量的参数。

**变量函数的语法:**

```go
func f(elem ...Type)
```

这里`...`操作符告诉 Golang 程序将 Type 的所有参数存储在 elem 参数中。然后，创建一个类型为[]类型的 elem 变量。因此，所有传递的值都存储在 elem 参数中，该参数是一个切片。切片也可以在参数中传递，而不是在参数列表中传递，因为 finally 函数正在将它们转换为切片。

更多信息可以参考高朗中的[变量函数](https://www.geeksforgeeks.org/variadic-functions-in-go/)

**使用变量函数的优势:**

*   在函数中传递切片非常容易。
*   当参数数量未知时很有用。
*   增加程序的可读性。

让我们看一些使用带有变量参数列表的函数的例子:

**例 1:**

```go
// Go program that uses a function
// with variable argument list
package main

// Importing required packages
import (
    "fmt"
)

// Variadic function to return 
// the sum of the numbers
func add(num ...int) int {
    sum := 0
    for j := range num {
        sum += j
    }
    return sum
}

func main() {
    fmt.Println("Sum =", add(1, 2, 3, 4, 5, 7, 8, 6, 5, 4))
}
```

**输出:**

```go
Sum = 45
```

**例 2:** 一个切片也可以作为自变量列表。

```go
// Go program that uses a function
// with variable argument list
// Using a slice as the argument list
package main

// importing required modules
import (
    "fmt"
)

// Function to check if an element
// is present in the list or not
func check(x int, v ...int) {

    flag := false
    index := 0
    for i, j := range v {
        if j == x {
            flag = true
            index = i
        }
    }

    if flag {
        fmt.Println("Element ", x, " found at index:", index)
    } else {
        fmt.Println("Element not present in the list")
    }
}
func main() {
    el := []int{1, 1, 2, 3, 4, 5, 6, 7, 8, 9}
    check(1, el...)
    check(10, el...)
}
```

**输出:**

```go
Element  1  found at index: 1
Element not present in the list

```