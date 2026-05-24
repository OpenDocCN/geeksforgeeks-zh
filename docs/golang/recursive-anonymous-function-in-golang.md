# Golang 中递归匿名函数

> 原文:[https://www . geesforgeks . org/recursive-anonymous-function-in-golang/](https://www.geeksforgeeks.org/recursive-anonymous-function-in-golang/)

递归是函数隐式或显式调用自身的过程，相应的函数称为递归函数。Go 语言支持名为 **[匿名功能](https://www.geeksforgeeks.org/anonymous-function-in-go-language/)** 的特殊功能。这是一个不包含任何名称的函数。它用于创建内联函数。递归函数也可以声明&定义为匿名。递归匿名函数也称为**递归函数字面量**。

**语法:**

```go
func(parameter-list)(return-type){
// code..
// call same function
// within the function
// for recursion
// Use return statement only
// if return-type are given.
return
}()

```

**示例:**

```go
// Golang program to show
// how to create an recursive
// Anonymous function
package main

import "fmt"

func main() {

    // Anonymous function
    var recursiveAnonymous func()
    recursiveAnonymous = func() {

        // Printing message to show the
        // function call and iteration.
        fmt.Println("Anonymous functions could be recursive.")

        // Calling same function 
        // recursively
        recursiveAnonymous()

    }

    // Main calling of
    // the function
    recursiveAnonymous()

}
```

**输出:**

```go
Anonymous functions could be recursive.
Anonymous functions could be recursive.
Anonymous functions could be recursive.
Anonymous functions could be recursive.
.
.
.
.
Infinite times function calls.

```

**例 2:**

```go
// Golang program to show
// how to create an recursive
// Anonymous function
package main

import (
    "fmt"
)

func main() {

    // Anonymous function
    var recursiveAnonymous func(int)

    // Passing arguments
    // to Anonymous function
    recursiveAnonymous = func(variable int) {

        // Checking condition
        // to return
        if variable == -1 {

            fmt.Println("Welcome to Geeks for Geeks!")
            return
        } else {

            fmt.Println(variable)

            // Calling same
            // function recursively
            recursiveAnonymous(variable - 1)
        }
    }

    // Main calling
    // of the function
    recursiveAnonymous(10)
}
```

**输出:**

```go
10
9
8
7
6
5
4
3
2
1
0
Welcome to Geeks for Geeks!

```