# Golang 中省略号(…)怎么用？

> 原文:[https://www . geesforgeks . org/如何使用省略号 in-golang/](https://www.geeksforgeeks.org/how-to-use-ellipsis-in-golang/)

Golang 中的三个点( **…** )被称为 Golang 中的省略号，用于[变量函数](https://www.geeksforgeeks.org/variadic-functions-in-go/)。用不同数量的参数调用的函数称为变量函数。或者换句话说，允许用户在变量函数中传递零个或多个参数。fmt。Printf 是变量函数的例子，它在开始时需要一个固定的参数，之后它可以接受任意数量的参数。

变量函数的最后一个参数总是使用省略号。这意味着它可以接受任何数量的参数。

**例 1:**

## Go

```go
// Golang program to show
// how to use Ellipsis (…)
package main

import "fmt"

func main() {
    sayHello()
    sayHello("Rahul")
    sayHello("Mohit", "Rahul", "Rohit", "Johny")
}

// using Ellipsis
func sayHello(names ...string) {
    for _, n := range names {
        fmt.Printf("Hello %s\n", n)
    }
}
```

**输出:**

```go
Hello Rahul
Hello Mohit
Hello Rahul
Hello Rohit
Hello Johny
```

**例 2:**

## Go

```go
// Golang program to show
// how to use Ellipsis (…)
package main

import (
    "fmt"
)

// using a variadic function
func find(num int, nums ...int) {
    fmt.Printf("type of nums is %T\n", nums)
    found := false
    for i, v := range nums {
        if v == num {
            fmt.Println(num, "found at index", i, "in", nums)
            found = true
        }
    }
    if !found {
        fmt.Println(num, "not found in ", nums)
    }
    fmt.Printf("\n")
}
func main() {

    // calling the function with
    // variable number of arguments
    find(89, 89, 90, 95)
    find(45, 56, 67, 45, 90, 109)
    find(78, 38, 56, 98)
    find(87)
}
```

**输出:**

```go
type of nums is []int
89 found at index 0 in [89 90 95]

type of nums is []int
45 found at index 2 in [56 67 45 90 109]

type of nums is []int
78 not found in  [38 56 98]

type of nums is []int
87 not found in  []
```