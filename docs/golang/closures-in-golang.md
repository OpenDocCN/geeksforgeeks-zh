# 戈朗的关闭

> 原文:[https://www.geeksforgeeks.org/closures-in-golang/](https://www.geeksforgeeks.org/closures-in-golang/)

Go 语言提供了一个被称为 [**匿名功能**](https://www.geeksforgeeks.org/anonymous-function-in-go-language/) 的特殊功能。匿名函数可以形成闭包。闭包是一种特殊类型的匿名函数，它引用在函数本身之外声明的变量。这类似于访问在函数声明之前可用的全局变量。

**例:**

```go
// Golang program to illustrate how
// to create a Closure
package main

import "fmt"

func main() {

    // Declaring the variable
    GFG := 0

    // Assigning an anonymous  
    // function to a variable 
    counter := func() int {
       GFG += 1
       return GFG
    }

    fmt.Println(counter())
    fmt.Println(counter())

}
```

**输出:**

```go
1
2

```

**解释:**变量 **GFG** 没有作为参数传递给匿名函数，但是函数可以访问它。在这个例子中，有一个小问题，因为任何其他将在 main 中定义的函数都可以访问全局变量 **GFG** ，并且它可以在不调用**计数器**函数的情况下更改它。因此关闭还提供了另一个方面，即**数据隔离**。

```go
// Golang program to illustrate how
// to create data isolation
package main

import "fmt"

// newCounter function to 
// isolate global variable
func newCounter() func() int {
    GFG := 0
    return func() int {
      GFG += 1
      return GFG
  }
}
func main() {
    // newCounter function is
    // assigned to a variable
    counter := newCounter()

    // invoke counter
    fmt.Println(counter())
    // invoke counter
    fmt.Println(counter())

}
```

**输出:**

```go
1
2

```

**解释:**闭包引用了变量 **GFG** 即使在 **newCounter()** 函数已经完成运行，但是 **newCounter()** 函数之外没有其他代码可以访问这个变量。这就是如何在函数调用之间保持数据的持久性，同时将数据与其他代码隔离开来。